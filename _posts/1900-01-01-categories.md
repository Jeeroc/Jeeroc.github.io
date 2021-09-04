---
layout: default
permalink: /categories/
title: "分类"
---

<ul class="categories">
   {% for cat in site.categories %}    
    <li>
        <a href="#{{ cat[0] }}">{{ cat[0] }}</a> <sup>{{ cat[1].size }}</sup>
    </li>
    {% endfor %}
   </ul>

<ul class="listing">
   {% for cat in site.categories %}
    <li class="listing-seperator" id="{{ cat[0] }}">{{ cat[0] }}</li>
    {% for page in cat[1] %}
    <li class="listing-item">
        <time datetime="{{ page.date | date:"%Y-%m-%d" }}">{{ page.date | date:"%Y-%m-%d" }}</time>
        <a href="{{ page.url }}" title="{{ page.title }}">{{ page.title }}</a>
    </li>
    {% endfor %}
{% endfor %}
</ul>
