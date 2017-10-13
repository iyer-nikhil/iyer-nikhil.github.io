---
layout: post
title:  "Zillow Prize: Predicting Real Estate"
date:   2017-09-15
desc: "Finding what goes into an accurate property estimate relative to sale price"
keywords: "Zillow, housing, property, Kaggle, python, estimate, logerror"
categories: [Python]
tags: [Python,Data,Boosting]
icon: icon-python
comments: true
---

When I initially joined a data science bootcamp, my dream was to compete in a [Kaggle](https://www.kaggle.com/) competition. For those of you that are unfamiliar with what that is, [Kaggle](https://www.kaggle.com/) hosts data science competitions for prizes if you are able to score the lowest on a particular benchmark given.

The grades for the competition allow you to compete against others for a chance at some serious prize money and Zillow just put out a $1 million dollar prize for someone who could use variables on a given property and beat their current estimate algorithm on pricing.

In order to get there though, they have a few barriers to entry:

* In order to compete in that leg, there is an initial leg of the tournament where only the top 100 advance. The goal of this first leg is to estimate how far off Zillow is at computing an estimate for a given property.

* Half the data hasn't even come out yet. They released 2016 data but ask you to predict the remaining months of 2017 - October, November, and December, for estimates and relative sale prices and will only release this at the beginning of October

* Once that is completed, if your model turns out to be in the top 100, then you have yourself a shot at their $1 million dollar prize!

For starters, I had to feature engineer something that would put me in a position to succeed. That started with examining certain features like the type of property below:  

   <!-- ![edit]({{ site.img_path }}/3steps/Image-1.jpg) -->
   <img src="{{ site.img_path }}/3steps/Image-1.jpg" width="70%" class="center-image">


On the left you can see how well Zillow was able to close the gap between their estimate and the final sale price of a home. Obviously they aren't the best with every home, or they wouldn't have this competition in the first place.
You can see as part of that map that areas in green tend to be pretty accurate, but the area in yellow that is boxed in red happens to be a blob where their estimate tends to be weak and be very far from estimating the final sale price correctly.
By doing some feature engineering I was able to see that the type of property became a huge indicator of whether or not an estimate was possible, as shown by the map on the right. Most of the properties tend to be single family residentials, but you will notice that for multi-unit housing, the Zillow estimate just does not do a good job in capturing the final sale price.

After weighting that with some level of significance in running a model (XGBoost) I was able to get into the top 800 of the competition while it was still around ~2500 people entered:

   <!-- ![edit]({{ site.img_path }}/3steps/800thplace.png) -->
   <img src="{{ site.img_path }}/3steps/800thplace.png" width="70%" class="center-image">
   
I did do some slight tweaking to the model's parameters and also found an interesting spot to potentially bifurcate the data. This is in the type of zoning for the property seen here:

   <!-- ![edit]({{ site.img_path }}/3steps/image5.png) -->
   <img src="{{ site.img_path }}/3steps/image5.png" width="70%" class="center-image">
   
By using the type of zoning, I could see that those properties with pool zoning would vastly differ in sale price from the estimate. It didn't just have to do with geographic location and I was better able to isolate this in my model.   

The biggest breakthrough came with running an average of various models with different weightings and node parameters. Using a combination of XGBoost and LightGBM by stacking (aka using in conjunction), I was able to bounce even higher in the competition to where I am today. The basic principle is below:

   <!-- ![edit]({{ site.img_path }}/3steps/image3.png) -->
   <img src="{{ site.img_path }}/3steps/image3.png" width="70%" class="center-image">

This is a basic diagram for stacking. As you can see, by taking the training data, passing it through models, and taking various weights of those models, we can produce a better overall predictor which vaulted me to the spot I am at today.
The exact combination of the models I did use are as follows:

   <!-- ![edit]({{ site.img_path }}/3steps/image4.png) -->
   <img src="{{ site.img_path }}/3steps/image4.png" width="70%" class="center-image">
   
So far got into the [top 11%](https://www.kaggle.com/nicksiyer)! But I'm still continually working at it. Thanks for tuning in and stick around for more to come as the second leg kicks off at midnight 10/3/2017!