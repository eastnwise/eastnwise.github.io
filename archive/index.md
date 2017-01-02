---
yout: default
title: Archive
---

<ul>
  {% for post in site.posts %}
    <li>
      <div><small>{{ post.date | date: "%Y-%m-%d | "}}</small><a href="{{ post.url }}">{{ post.title }}</a></div>
    </li>
  {% endfor %}
</ul>

