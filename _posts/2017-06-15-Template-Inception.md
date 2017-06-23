---
layout: post
title: "Template Inception"
description: "Alternative to web site generation server-side using templates"
category:
tags: []
---
{% include JB/setup %}
There are some instances when you need to serve your users with a web site, where most of the content is stale for atleast few hours, days or week. If you have such a scenario, what follows is one approach to satisfy that requirement.

The site we want to build is to display a simple list of top box office [hits](http://www.imdb.com/chart/boxoffice) for the weekend. 

The approach for site generation we take is to use a Python based scraper that uses the [Jinja](http://jinja.pocoo.org/) template engine to populate a [Vue.js](https://vuejs.org/) file that is then used by the [index.html](https://github.com/mobileraj/jinja2vue/blob/master/page/index.html) to display the content.

![img]({{ site.url }}/assets/screenshot.png)

The following diagram illustrates the various files used in this post.
![img2]({{ site.url }}/assets/t.png)

The [repo](https://github.com/mobileraj/jinja2vue) accompanying this post has the files and the entire web site that was generated.
