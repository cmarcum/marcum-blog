---
layout: default
title: Blog Posts by Tag
---

{% assign tags = site.tags | sort %}
{% for tag in tags %}
  <h3 id="{{ tag[0] | slugify }}">{{ tag[0] | capitalize }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}