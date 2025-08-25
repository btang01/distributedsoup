---
layout: default
title: Business & Strategy
---

# Business & Strategy

{% assign business_posts = site.posts | where_exp: "post", "post.categories contains 'strategy' or post.categories contains 'business' or post.categories contains 'economics' or post.categories contains 'branding'" %}
{% assign business_years = business_posts | group_by_exp: "post", "post.date | date: '%Y'" | reverse %}

{% for year in business_years %}
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