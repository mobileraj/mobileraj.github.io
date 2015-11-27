---
layout: post
title: "Atari Vax Email Network Analysis"
description: ""
category: 
tags: []
---
{% include JB/setup %}
I saw the email posting from <a href="http://www.jmargolin.com/"> Jed Margolin</a> about his emails from Atari.
I wanted to see if I can visualize the email as a network. Here is the brief writeup of this mini-project.

### Extracting Data
The emails are in text format for the years 1983 to 1992. Its available on his <a href="http://www.jmargolin.com/vmail/vmail.htm">web site</a>
I wrote a simple Python script to extract the tuple
(from person, to person, timestamp)
for the entire set of email text files on his site. Ref#2 provides the python source for it. 
It uses a simple state machine model of 3 states - from/to/reset to extract and populate the data list which I save it as pickle.

### Getting a network
I then used <a href="http://networkx.github.io/"> NetworkX </a> library.

![graph](https://github.com/mobileraj/atariGraph/blob/master/vaxemail.png?raw=true)
To be continued....


### References
[1] Source of the data - http://www.jmargolin.com/vmail/vmail.htm

[2] Python notebook to parse text and extract network list -https://github.com/mobileraj/atariGraph/blob/master/main.ipynb 

[3] Github repo for this project - https://github.com/mobileraj/atariGraph

[4] Python notebook to get a GraphML file - https://github.com/mobileraj/atariGraph/blob/master/PyGraphML.ipynb

\[5] Python notebook for doing graph analysis - https://github.com/mobileraj/atariGraph/blob/master/Graph%20Analysis.ipynb
