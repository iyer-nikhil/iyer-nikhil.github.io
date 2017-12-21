---
layout: post
title:  "NYC Open Data: Examining MTA Turnstile Data"
date:   2017-07-11
desc: "Exploratory data analysis on subway turnstile information"
keywords: "MTA, turnstile, data, frequency"
categories: [Data Science]
tags: [Python,Data,Pandas]
icon: icon-python
comments: true
---

NYC Open Data puts out a lot of neat information online. One of these pieces is MTA data that shows how many people go through various turnstiles across NYC's boroughs. I thought it was a cool EDA to check out and especially the subway line that is relatively new to the city and one close to my heart: the 2nd Ave Q line.

This line is relatively new, only open as of January 1st, 2017 for parts that go through 72nd and 96th street. After loving this area so much, having friends who live in this area as well, I thought it would be cool to check out exactly how many people go in and out of this area.

As you can see from the image below, it is relatively consistent goings for turnstiles for different days of the week:

   <!-- ![edit]({{ site.img_path }}/3steps/img1g2.jpg) -->
   <img src="{{ site.img_path }}/3steps/img1g2.jpg" width="70%" class="center-image"> 
     
As you can see from these 4 weeks of data that I obtained, they follow a similar pattern, with ridership relatively slow on mondays, picking up through midweek, and dropping off by the weekend. It is fascinating to see that for some weeks, there is a jump from Saturday into Sunday but for some weeks, there is a dip. This might be due to attractions or certain weekend events that restaurants have in the area. I'd also like to see how street fairs in the area could potentially impact this graph.

Here is another visual in the form of a bar graph to give you a much better side by side comparison of days in different weeks:

   <!-- ![Bar graph of subway entries for 86th St]({{ site.img_path }}/3steps/img1g3.jpg) -->
   <img src="{{ site.img_path }}/3steps/img1g3.jpg" width="70%" class="center-image"> 
   


One interesting thing to note is that these are just entries into the subway and not exits. Why did I choose to leave exits alone? Well its because even when looking at multiple stations, the entries and exits on a weekly basis do not match at all.

   <!-- ![edit]({{ site.img_path }}/3steps/img1g4.jpg) -->
   <img src="{{ site.img_path }}/3steps/img1g4.jpg" width="70%" class="center-image"> 
   
That's because in some cases, people use the emergency exits on the turnstiles, which do not count the number of people. So having the entries is for the most part accurate because that barrier is set. Using exits would not be doing the data justice.

Thank you for listening to my intro EDA for MTA Turnstiles. If you want to check out my [GitHub](https://github.com/nicksiyer/mta_turnstiles) please feel free! This is my first project working with data and I urge you to check out my other projects that cover more extensively machine learning tools that I learned throughout the Metis program.
