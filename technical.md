---
layout: page
title: Technical Writing
permalink: /technical.html
---

{% assign tech_posts = site.posts | where_exp: "post", "post.categories contains 'technical' or post.categories contains 'tech'" %}
{% assign tech_years = tech_posts | group_by_exp: "post", "post.date | date: '%Y'" | reverse %}

{% for year in tech_years %}
<div class="year-label">{{ year.name }}</div>

<div class="post-grid">
{% for post in year.items %}
  <a href="{{ post.url | relative_url }}" class="post-box">
    <div class="post-date">{{ post.date | date: "%b %-d" }}</div>
    <div class="post-title">{{ post.title }}</div>
  </a>
{% endfor %}
</div>
{% endfor %}

{% if tech_posts.size == 0 %}
<div class="coming-soon">Coming soon.</div>
{% endif %}