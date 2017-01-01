yout: default
title: Archive
---

<ul>
  {% for post in site.posts %}
    <li>
      <div><small>{{ post.date | date_to_string }}</small><a href="{{ post.url }}">{{ post.title }}</a></div>
    </li>
  {% endfor %}
</ul>
