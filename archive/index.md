---
layout: default
title: 글 저장
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <div><small>{{ post.date | date_to_string }}</small></div>
    </li>
  {% endfor %}
</ul>
