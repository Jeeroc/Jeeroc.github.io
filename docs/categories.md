---
layout: default
permalink: /categories/
title: "分类"
---

<ul class="categories">
   {% for cat in page.categories %}    
    <li>
        <a href="#{{ cat[0] }}">{{ cat[0] }}</a> <sup>{{ cat[1].size }}</sup>
    </li>
    
   {% endfor %}
   </ul>

<ul class="listing">
 {% for cat in page.categories %}
    <li class="listing-seperator" id="{{ cat[0] }}">{{ cat[0] }}</li>
    {% for p in cat[1] %}
    <li class="listing-item">
        <time datetime="{{ p.date | date:"%Y-%m-%d" }}">{{ p.date | date:"%Y-%m-%d" }}</time>
        <a href="{{ p.url }}" title="{{ p.title }}">{{ p.title }}</a>
    </li>
    {% endfor %}
 {% endfor %}
</ul>
