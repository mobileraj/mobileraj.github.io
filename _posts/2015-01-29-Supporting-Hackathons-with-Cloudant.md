---
layout: post
title: "Supporting hackathons with Cloudant"
description: ""
category: 
tags: []
---
{% include JB/setup %}
As I start to attend hackathons around supporting devs to build apps with [IBM Bluemix](http://bluemix.net), I kept being asked how to use some public dataset within mobile and web apps. When I was in San Francisco, I heard about the [Open Data](https://data.sfgov.org/) project. I looked at the Bicycle parking data [set](https://data.sfgov.org/Transportation/Bicycle-Parking-Public-/w969-5mn4) and got that into [Cloudant](http://cloudant.com) for use at hackathons.

The URL for accessing the data is off my Cloudant DB
https://mobileraj.cloudant.com/sfbikelots/

I also created _index so you can use Cloudant [Query](https://docs.cloudant.com/cloudant_query.html)
Finding all lots on Ellis:
{% highlight bash %}
curl -H "Content-Type: application/json" https://mobileraj.cloudant.com/sfbikelots/_find -X POST -d
     '{
        "selector": {"street":"ELLIS"},
	"fields": ["street","address","mo_installed","yr_installed","placement","coords","latitude"]
     }'
{% endhighlight %}

[Geo](https://docs.cloudant.com/geo.html#example:-querying-a-cloudant-geo-index) specific queries are also supported -
Getting all entries within a boundingbox:
{% highlight bash %}
https://mobileraj.cloudant.com/sfbikelots/_design/SpatialView/_geo/lots?bbox=37,-122,37.8,-122.5&include_docs=true
{% endhighlight %}

Email or tweet if you want to know more...