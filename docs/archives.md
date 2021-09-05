---
layout: default
permalink: /archives/
title: "归档"
date: 1900-01-01
---
<ul>
  {% assign sorted = site.pages | sort: 'date' | reverse %}
  {% for page in sorted %}
    {% unless page.next %}
      <h2> {{ '!' }} </h2>
      <h2>{{ page.date | date: '%Y年' }}</h2>
     {% else %}
      {% capture year %}{{ page.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ page.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h2> {{ '!!' }} </h2>
        <h2>{{ page.date | date: '%Y年' }}</h2>
      {% endif %}
    {% endunless %}
      <li>{{ page.date | date:"%Y年%m月%d日：" }} <a href="{{ page.url }}">{{ page.title }}</a></li>
  {% endfor %}

</ul>
