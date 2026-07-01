---
layout: default
title: "博客"
lang: zh
permalink: /zh/blog/
---

{% if site.show_excerpts %}
  {% include home.html %}
{% else %}
  {% include archive.html title="文章" %}
{% endif %}
