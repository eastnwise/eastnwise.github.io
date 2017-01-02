---
layout: default
page_title: Search
---
<!--Html Elements for Search -->
<div id="search-container">
<h1> Search </h1>
<input type="text" id="search-input" placeholder="search..." size="80" style="height:20px;">
<ul id="results-container"></ul>
</div>

<!-- Script pointing to jekyll-search.js -->
<script src="{{site.baseurl}}/search/jekyll-search.min.js" type="text/javascript"></script>


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
