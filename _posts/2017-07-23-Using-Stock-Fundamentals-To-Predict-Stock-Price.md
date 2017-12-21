---
layout: post
title:  "Predicting Stock Price Using Key Statistics"
date:   2017-07-23
desc: "Scraping S&P 500 statistics on Yahoo Finance"
keywords: "Yahoo, Finance, stocks, linear regression, regression, fundamentals"
categories: [Python]
tags: [Python,Data,Scrapy,Finance,Linear Regression]
icon: icon-python
comments: true
---

Not having a lot of experience working in finance, I wanted to know what exactly went into the pricing of a stock. During a trading day, a given stock will go up or down depending on the supply and demand of shares, and is always moving towards an optimal price that factors in the value of a company dependent on what investors feel it is worth.  

But removing for news and sticking solely to the quantitative fundamentals, the question was, "could I use a regressive model to judge if a stock is over or underpriced in the market?" Obviously this is a very naive approach that does not factor main factors such as recent news as well as any earnings outlook that may have been priced in. But I decided to give it a shot and see what happened.

By setting up a scraper to parse Yahoo Finance key statistics into a .json file, I took a look at the following metrics of a sample stock :

  <!-- ![edit]({{ site.img_path }}/3steps/stats2.png) --> <!-- ![edit]({{ site.img_path }}/3steps/stats1.png) --> <!-- ![edit]({{ site.img_path }}/3steps/stats2.png) --> <!-- ![edit]({{ site.img_path }}/3steps/stats1.png) --> 
  <img src="{{ site.img_path }}/3steps/stats2.png" width="23%"> <img src="{{ site.img_path }}/3steps/stats1.png" width="23%"> <img src="{{ site.img_path }}/3steps/stats2.png" width="23%"> <img src="{{ site.img_path }}/3steps/stats1.png" width="23
  %">
   
   
   