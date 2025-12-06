---
layout: page
title: WhatAppChannel
permalink: /WhatAppChannel/
---

# Blog

{% for post in site.posts %}
  {% if post.categories contains "blog" %}
  - **[{{ post.title }}]({{ post.url }})**  
    <small>{{ post.date | date: "%b %d, %Y" }}</small>
  {% endif %}
{% endfor %}
