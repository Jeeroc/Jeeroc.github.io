---
layout: default
permalink: /archives/
title: "归档"
date: 1900-01-01
---
<ul>
  {% assign sorted = site.pages | sort: 'date' | reverse %}
  {% for page in sorted %}
    <li>{{ page.date | date:"%Y年%m月%d日：" }} <a href="{{ page.url }}">{{ page.title }}</a></li>
  {% endfor %}

</ul>
