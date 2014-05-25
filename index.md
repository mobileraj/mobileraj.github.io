---
layout: page
title: Gurukulam
tagline: learnings of mobileraj
---
#### Learnings

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

#### Creations
<a href="https://github.com/mobileraj/findatech">Findatech</a> - A simple Cordova hybrid app to display results of geo queries supported by Cloudant. The scenario is that of *within* and *overlap* queries

#### Fun
More to come
