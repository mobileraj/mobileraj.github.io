---
layout: post
title: "Analyzing Buffett Chairman Letters using Topic Models"
description: ""
category: 
tags: []
---
{% include JB/setup %}
I have had a fascination with [Warren Buffett](https://en.wikipedia.org/wiki/Warren_Buffett) since I landed in the US and learned about him form a mentor of mine. Although I had heard of his famous chairman letters and how accessible they were, I was more interested in his bio and other content about him.

I finally broke down this year and started reading his letters which are publicly available on [Berkshire Hathaway site](http://www.berkshirehathaway.com/letters/letters.html). This holiday season, I went and tried to visualize the themes of his writing using [Topic Models](http://www.cs.columbia.edu/~blei/topicmodeling.html). What follows is a write up of the work I did.

### Downloading data
I used wget and a simple python script to download the PDFs (since 1998) and extract the text using Ghostscript. For the plain HTML ones (pre1998) I used html2text and then extracted text. Since the writing were plain text and no fancy images etc. it was easy to get the data. Once extracted I had original letters in text file format from 1977-2014, a total of 38 files.
### Learning about Topic Models
A separate technical note will follow this where I will document my learnings of this topic.
 
### Topic Model tooling
I was back to using R, python to see what LDA/Topic Model library did the job I was looking for. I explored lda & topicmodel & tm libraries in R and LDA & gensim libraries in Python. In the end I ended up using [Mallet](http://mallet.cs.umass.edu/topics.php) from [UMass](http://umass.edu) which was simple and performant for the documents  had. Both Python and R libraries took over 2 minutes to process the 38 docs for 500 iterations, while Mallet did the job in 10s of secs. A screenshot of using the tool on my Linuxtop.

![Mallet at work](https://raw.githubusercontent.com/mobileraj/mobileraj.github.io/master/_site/assets/Mallet_ScreenShot.png)
 
### Exploring dataset
Before I started looking at the topics and running LDA or one of its variants, I wanted to see how the word distribution looked like, so I used R to get the wordcloud which helped me to refine my stopword selection to be used in Mallet.

![Word Cloud](https://raw.githubusercontent.com/mobileraj/mobileraj.github.io/master/_site/assets/wordcloud.png)

For completion, here the are the top 10 words in bar plot-
![Wordbars](https://raw.githubusercontent.com/mobileraj/mobileraj.github.io/master/_site/assets/wordbars.png)

### Topic based analysis of Buffet letters
Mallet is very easy to use and once you have the text documents primed, its a breeze. Since most of the cursory read of the letters suggested that there were similar themes that Buffett was writing, I wanted to understand if number of topics had any impact to how the themes evolved over the past 30+ years in Buffett's writing. I tried 2,5,10,20,25,50 topics and ended up pruning 5,10,20 topics to see the evolution and did most of the analysis with 5 topics model. I show the HTML output produced by Mallet for 5 topics model with top 10 words
![Mallet 5Topic Out](https://raw.githubusercontent.com/mobileraj/mobileraj.github.io/master/_site/assets/5topics.png)

Then I proceeded to plot the topics over time for the 5,10,20 topics models. 20 topics model with top 3 topics per letter over time -
![20topics](https://raw.githubusercontent.com/mobileraj/mobileraj.github.io/master/_site/assets/trial1.png)

10 topics model with top 3 topics per letter-
![10topics](https://raw.githubusercontent.com/mobileraj/mobileraj.github.io/master/_site/assets/trial2.png)

5 topics model with top 3 topics per letter-
![5topics](https://raw.githubusercontent.com/mobileraj/mobileraj.github.io/master/_site/assets/trial3.png)

### Moneyshot
My favourite tool from the viz toolchest has been multi-dimensional scaling (MDS) for higher dimensional data for the last decade and so I took the 5 topics model and tried to visualize the the letters over time using how each letter contributes to the topic (probablities). This produced the most cool graph clustering the 70s,80s,90s,2000s loosely.
![MDS 5topics](https://raw.githubusercontent.com/mobileraj/mobileraj.github.io/master/_site/assets/DistPlot.png)

Email or tweet if you want to know more...
