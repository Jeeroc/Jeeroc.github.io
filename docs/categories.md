---
layout: default
permalink: /categories/
title: "分类"
---
<ul class="listing">
 {% for page in site.pages %}
 {% for cat in page.categories %}
    <li class="listing-seperator" id="{{ cat }}">{{ cat }}</li>
    {% for p in site.pages %}
    {{p.categories}}
    {{cat}}
    {if p.categories contains cat}
    <li class="listing-item">
        <time datetime="{{ p.date | date:"%Y-%m-%d" }}">{{ p.date | date:"%Y-%m-%d" }}</time>
        <a href="{{ p.url }}" title="{{ p.title }}">{{ p.title }}</a>
    </li>
    {% endif %}
    {% endfor %}
 {% endfor %}
 {% endfor %}
</ul>
