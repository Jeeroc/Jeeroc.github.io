---
layout: default
title: 标签
permalink: /tags/
---
<ul class="tags">
   {% for tag in site.tags %}    
    <li>
        <a href="#{{ tag[0] }}">{{ tag[0] }}</a> <sup>{{ tag[1].size }}</sup>
    </li>
    {% endfor %}
   </ul>

<ul class="listing">
   {% for tag in site.tags %}
    <li class="listing-seperator" id="{{ tag[0] }}">{{ tag[0] }}</li>
    {% for page in tag[1] %}
    <li class="listing-item">
        <time datetime="{{ page.date | date:"%Y-%m-%d" }}">{{ page.date | date:"%Y-%m-%d" }}</time>
        <a href="{{ page.url }}" title="{{ page.title }}">{{ page.title }}</a>
    </li>
    {% endfor %}
{% endfor %}
</ul>
