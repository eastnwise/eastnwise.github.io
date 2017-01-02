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

<ul>
  {% for post in site.posts %}

    <!-- {% unless post.next %} -->
    <!--   <h3>{{ post.date | date: '%Y-%m' }}</h3> -->
    <!-- {% else %} -->
      {% capture month %}{{ post.date | date: '%Y-%m' }}{% endcapture %}
      {% capture nmonth %}{{ post.next.date | date: '%Y-m%' }}{% endcapture %}
      {% if month != nmonth %}
        <h3>{{ post.date | date: '%Y-%m' }}</h3>
      {% endif %}
    {% endunless %}

    <li>{{ post.date | date:"%d" }} <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

{% for post in site.posts %}
    {% capture month %}{{ post.date | date: '%Y-%m' }}{% endcapture %}
    {% capture nmonth %}{{ post.next.date | date: '%Y-%m' }}{% endcapture %}
        {% if month != nmonth %}
            <!-- {% if forloop.index != 1 %}</ul>{% endif %} -->
            <h3>{{ post.date | date: '%Y-%m' }}</h3><ul>
        {% endif %}
    <time>{{ post.date | date: "%d" }}</time>
    <li><a href="{{ post.url }}">{{ post.title }}</a></li></ul>
{% endfor %}
