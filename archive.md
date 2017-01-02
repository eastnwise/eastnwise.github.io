---
layout: default
title: Archive
permalink: /archive/
---

<!-- <ul> -->
<!--   {% for post in site.posts %} -->
<!--     <li> -->
<!--       <div><small>{{ post.date | date: "%Y-%m-%d | "}}</small><a href="{{ post.url }}">{{ post.title }}</a></div> -->
<!--     </li> -->
<!--   {% endfor %} -->
<!-- </ul> -->
<h1>Archive</h1>
<!--Html Elements for Search -->
<div id="search-container">
<input type="text" id="search-input" placeholder="search...">
<ul id="results-container"></ul>
</div>

<!-- Script pointing to jekyll-search.js -->
Search: <script src="{{site.baseurl}}/search/jekyll-search.min.js" type="text/javascript"></script>


<script type="text/javascript">
      SimpleJekyllSearch({
        searchInput: document.getElementById('search-input'),
        resultsContainer: document.getElementById('results-container'),
        json: '{{ site.baseurl }}/search/search.json',
        searchResultTemplate: '<li><a href="{url}" title="{desc}">{title}</a></li>',
        noResultsText: 'No results found',
        limit: 10,
        fuzzy: false,
        exclude: ['Welcome']
      })
</script>

<ul>
{% for post in site.posts %}
    {% capture month %}{{ post.date | date: '%Y-%m' }}{% endcapture %}
    {% capture nmonth %}{{ post.next.date | date: '%Y-%m' }}{% endcapture %}
        {% if month != nmonth %}
            <h3>{{ post.date | date: '%Y-%m' }}</h3>
        {% endif %}
      <li>{{ post.date | date: "%Y-%m-%d | "}} <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
