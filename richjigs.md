---
layout: page
title: RichJigs
---

<!-- <h1>{{ page.title }}</h1> -->

{% for post in site.richjigs %}
  <ul>
    <li><a href="{{ post.url }}">{{ post.date | date: "%B %d, %Y" }} - {{ post.title }}</a></li>
  </ul>
{% endfor %}

