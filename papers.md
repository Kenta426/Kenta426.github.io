---
layout: page
title: Papers
description: Publications, preprints, and theses
image: /assets/images/manuscript.jpeg
---


<div class='papers'>


  {% assign categories = "Selected Papers"|"Publication in Statistics"|"Preprint"| split: "|" %}


  {% for cat in categories %}

  <h1>{{ cat }} </h1>
  (A full list can be found <a href='https://scholar.google.com/citations?user=xBePphQAAAAJ&hl=en'>here</a>.)
  {% assign publications = site.papers | sort: "date" | reverse | where_exp: "item", "item.category == cat"%}

  <table class='papers-table'>
  {% for pub in publications %}
  <tr>
  <td>
   <div class="pubtitle">{{ pub.title }}</div>
    <div class="pubauthors">{{ pub.authors }}.</div>
    {% if pub.link != nil %}
       <a href='{{ pub.link }}'>arXiv</a>,
    {% endif %}
    {% if pub.publication != nil %}
       <a href='{{ pub.link2 }}'><em>{{ pub.publication }},</em></a>
    {% endif %}
    {% if pub.year != nil %} 
        <em>{{ pub.year }}</em> 
    {% endif %}
    {% if pub.code != nil %} 
       &middot; <a href='{{ pub.code }}'>code</a>
    {% endif %}
    {% if pub.slide != nil %} 
       &middot; <a href='{{ pub.slide }}'>slide</a>
    {% endif %}
    {% if pub.highlight != nil %} 
       <br><span id='highlight'>{{ pub.highlight }}</span> 
    {% endif %}
  </td>
  </tr>
  {% endfor %}
  </table>
   
  {% endfor %}


</div>

<!-- {% capture markdown_content %}
# Software 

Aside from the code associated with the papers above, here are some packages that I maintain. 

<span style="color: black; font-weight: bold">testing-by-betting</span>: A python package which implements various methods for sequential, nonparametric hypothesis testing using various tools from game-theoretic probability and statistics. [[github]()] [[pypi]()]

<span style="color: black; font-weight: bold">xbounds</span>: A lightweight python package for Extreme Bounds Analysis. Computes both Leamer and Sala-i-Martin robustness criteria. Handles fixed-effects and multiprocessing. [[github]()] [[pypi]()]

{% endcapture %}
{{ markdown_content | markdownify }} -->



