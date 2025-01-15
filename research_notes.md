---
layout: page
title: Notes
---


<div class='notes'>
{% assign notesByYear = site.notes | where_exp: "item", "item.status == 'published'" |
sort: "date" | reverse | group_by_exp:"item", "item.date | date: '%Y'"%}

{% for year in notesByYear %}
  <h1>{{ year.name }}</h1>
  <ul>
      {% for post in year.items %}
        <li>
            {{ post.date | date: "%m/%d"}} - <a href="{{ post.url }}">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
{% endfor %}
</div>