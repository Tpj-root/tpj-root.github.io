---
layout: page
title: WhatAppChannel
permalink: /WhatAppChannel/
---

# WhatsApp Channel

{% for post in site.posts %}
  {% if post.categories contains "WhatAppChannel" and post.published != false %}
  - **[{{ post.title }}]({{ post.url }})**  
    <small>{{ post.date | date: "%b %d, %Y" }}</small>
  {% endif %}
{% endfor %}

