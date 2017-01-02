---
yout: default
title: Archive
---

<!-- <ul> -->
<!--   {% for post in site.posts %} -->
<!--     <li> -->
<!--       <div><small>{{ post.date | date: "%Y-%m-%d | "}}</small><a href="{{ post.url }}">{{ post.title }}</a></div> -->
<!--     </li> -->
<!--   {% endfor %} -->
<!-- </ul> -->

{% for post in site.posts %}
    {% capture month %}{{ post.date | date: '%m%Y' }}{% endcapture %}
    {% capture nmonth %}{{ post.next.date | date: '%m%Y' }}{% endcapture %}
        {% if month != nmonth %}
            {% if forloop.index != 1 %}</ul>{% endif %}
            <h3>{{ post.date | date: '%Y-%m' }}</h3><ul>
        {% endif %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    <time>{{ post.date | date: "%d" }}</time>
{% endfor %}
