---
layout: default
permalink: /categories/
title: "分类"
---

<ul class="tags">
    {% for cat in site.categories %}
    <li>
        <a href="#{{ cat[0] }}">{{ cat[0] }}</a> <sup>{{ cat[1].size }}</sup>
    </li>
    {% endfor %}
</ul>

<ul class="listing">
    {% for cat in site.categories %}
    <li class="listing-seperator" id="{{ cat[0] }}">{{ cat[0] }}</li>
    {% for post in cat[1] %}
    <li class="listing-item">
        <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
        <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    </li>
    {% endfor %}
{% endfor %}
</ul>
