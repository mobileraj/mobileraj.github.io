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

#### Musings
More to come

#### Creations
More to come