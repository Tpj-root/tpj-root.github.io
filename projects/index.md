---
layout: page
title: Projects
permalink: /projects/
---

# Projects

{% for post in site.posts %}
  {% if post.categories contains "project" %}
  - **[{{ post.title }}]({{ post.url }})**  
    <small>{{ post.date | date: "%b %d, %Y" }}</small>
  {% endif %}
{% endfor %}
