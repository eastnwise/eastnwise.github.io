---
layout: default
title: 글모음
permalink: /archive/
---

<ul>
  {% for post in site.posts %}
    <li>
      {{ post.date | date: "%Y-%m-%d %L:%M %P}} <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
