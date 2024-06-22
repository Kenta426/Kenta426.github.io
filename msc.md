---
layout: page
title: Msc
---


<div class='notes'>
{% assign notesByYear = site.notes | where_exp: "item", "item.status == 'published'" |
sort: "date" | reverse | group_by_exp:"item", "item.date | date: '%Y'"%}

{% for year in notesByYear %}
  <h1>{{ year.name }}</h1>
    -　全て真夜中の恋人たち
    - 
{% endfor %}
</div>