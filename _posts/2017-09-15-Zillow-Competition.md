---
layout: post
title:  "Zillow Prize - The Veracity of Real Estate"
date:   2017-09-15
desc: "Using the Zillow-Kaggle competition to predict property estimates"
keywords: "Zillow, housing, property, Kaggle, python"
categories: [Python]
tags: [Python,Data,Boosting]
icon: icon-python
comments: true
---

When I initially joined a data science bootcamp, my dream was to compete in a [Kaggle](https://www.kaggle.com/) competition. For those of you that are ufamiliar with what that is, [Kaggle](https://www.kaggle.com/) hosts data science competitions for prizes if you are able to score the lowest on a particular benchmark given.

The grades for the competition allow you to compete against others for a chance at some serious prize money and Zillow just put out a $1 million dollar prize for someone who could use variables on a given property and beat their current estimate algorithm on pricing.

In order to get there though, they have a few barriers to entry:

* In order to compete in that leg, there is an initial leg of the tournament where only the top 100 advance. The goal of this first leg is to estimate how far off Zillow is at computing an estimate for a given property.

* Half the data hasn't even come out yet. They released 2016 data but ask you to predict the remaining months of 2017 - October, November, and December, for estimates and relative sale prices and will only release this at the beginning of October

* Once that is completed, if your model turns out to be in the top 100, then you have yourself a shot at their $1 million dollar prize!

Seems simple enough right?

So I decided to give it a shot! So far got into the [top 8%](https://www.kaggle.com/nicksiyer)! But I'm still continually working at it every day.

But how did I even get to that point? Well for starters, I had to feature engineer something that would put me in a position to succeed. That started with examining what I had going with the data I was given:    

   <!-- ![edit]({{ site.img_path }}/3steps/Image-1.jpg) -->
   <img src="{{ site.img_path }}/3steps/Image-1.jpg" width="75%">


On the left you can see how well Zillow was able to close the gap between their estimate and the final sale price of a home. Obviously they aren't the best with every home, or they wouldn't have this competition in the first place.
You can see as part of that map that areas in green tend to be pretty accurate, but the area in yellow that is boxed in red happens to be a blob where their estimate tends to be weak and be very far from estimating the final sale price correctly.
By doing some feature engineering I was able to see that the type of property became a huge indicator of whether or not an estimate was possible, as shown by the map on the right. Most of the properties tend to be single family residentials, but you will notice that for multi-unit housing, the Zillow estimate just does not do a good job in capturing the final sale price.

So that helped actually get me pretty far, for starters, in the competition. After weighting that with some level of significance in running a model (thats right, my favorite machine learning model, XGBoost!) I was able to get into the top 800 of the competition while it was still around ~2500 people entered:

   <!-- ![edit]({{ site.img_path }}/3steps/800thplace.png) -->
   <img src="{{ site.img_path }}/3steps/800thplace.png" width="65%">
   
I did do some slight tweaking to the model's parameters as you can see it took me 4 tries to eventually place here, but hey, its not a bad start!

