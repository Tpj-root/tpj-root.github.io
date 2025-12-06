---
layout: page
title: Blog
permalink: /blog/
---

# Blog

{% for post in site.posts %}
  {% if post.categories contains "blog" and post.published != false %}
  - **[{{ post.title }}]({{ post.url }})**  
    <small>{{ post.date | date: "%b %d, %Y" }}</small>
  {% endif %}
{% endfor %}
