---
layout: post
title: "WhatsApp PS90 Group Analysis - Part1"
description: "Initial analysis of my highschool Chat group"
category: 
tags: []
---
{% include JB/setup %}
<i>Updated on Nov2, to include additional data </i>

I graduated from P.S.Senior Secondary School in Madras, India - class of 1990. Recently I was added to the WhatsApp group of our class by an old friend. I was added as of October 14 2016.
What follows is my initial analysis of the message flow through November 2 2016. I was warned that this group was active and voluminous compared to other groups...

Here is the daily flow of messages since i joined till today...
<br/><img src="http://mobileraj.github.io/assets/ts1.png" width="700">

Looking at how active messages are by the hour of the day (remember the times are my local time in CST). The members are globally distributed between US (east to west), Middle East, India and Singapore.
<br/><img src="http://mobileraj.github.io/assets/hr_hist.png" width="600">

Now if I looked at how the flow of messages were by day of the week and by hour of the day, I get an interesting pattern
<br/><img src="http://mobileraj.github.io/assets/wk_heatmap.png" width="600">

I also looked at how the messages per member of the group was distributed. The intuition that it will follow a  powerlaw was correct, given there are few who are way more active and occupy the window at any given time than the rest. I used the poweRlaw package to easily plot it out.
<br/><img src="http://mobileraj.github.io/assets/power.png" width="800">

Without a serious textual analysis, I ended up just parsing out the messages with filters to show the word cloud
<br/><img src="http://mobileraj.github.io/assets/wc.png" width="600">

I also wanted to see if I can create a network based on name references in the message. Since Whatsapp, doesnt preserve the the inherent structure of conversation thread, it is just a big log export of text as it appears, I only claim an edge between two nodes (friends) if the sender mentions another member of the group - either by real name or using nickname. This method is faulty still, as it misses variances of names that I have lost track of (it was 22 years ago that I knew the gang) or new nicknames they have given to eachother.

This analysis yielded the following spring layout -
<br/><img src="http://mobileraj.github.io/assets/Network1.png">

I also created a visualization of the evolving network, which you can see on Youtube
<br/>
<iframe width="560" height="315" src="https://www.youtube.com/embed/CWOCAl8n50Y" frameborder="0" allowfullscreen></iframe>

The best part of this was me trying to understand how WhatsApp stores the messages and how we can parse it relatively straightforward. I am looking for the conversation thread structure so I could do some network modeling, but alas I am unable to find the fight metadata in the export of the chat history to extract that information.

I will keep trying to see if I can.....until then....