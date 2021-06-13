---
layout: page
title: Search
permalink: /search/
search: exclude
---

<div id="search-container">
    <input type="text" id="search-input" placeholder="Type to search...">
    <ul id="results-container"></ul>
</div>

<script src="{{ site.baseurl }}/simple-jekyll-search.min.js" type="text/javascript"></script>

<script>
    SimpleJekyllSearch({
    searchInput: document.getElementById('search-input'),
    resultsContainer: document.getElementById('results-container'),
    searchResultTemplate: '<div style="text-align: left !important;"><a href="{url}"><h1 style="text-align:left !important;">{title}</h1></a><span style="text-align:left !important;">{date}</span></div>',
    json: '{{ site.baseurl }}/search.json',
    sortMiddleware: function(a, b) {
      var astr = String(a.section) + "-" + String(a.caption);
      var bstr = String(b.section) + "-" + String(b.caption);
      return astr.localeCompare(bstr)
    }
    });
</script>
