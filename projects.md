---
title: "Projects"
layout: default
---

<article markdown="1">
<header><h1>Projects</h1></header>

A small, curated list of things I've built or am actively working on.

{% assign projects = site.projects | sort: "order" %}
<ul class="projects-list" markdown="1">
{% for project in projects %}
  <li markdown="1">
**[{{ project.title }}]({{ project.url | relative_url }})**{% if project.subtitle %} <span style="opacity:.6; font-weight:400">({{ project.subtitle }})</span>{% endif %} — {{ project.tagline }}
  </li>
{% endfor %}
</ul>

</article>
