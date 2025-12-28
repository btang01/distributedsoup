---
layout: default
title: Home
---

# Distributed Soup

Ideas at the intersection of **technology, strategy**, and **innovation**.

I'm **Brian Tang**, a current Customer Engineer at Google with an MBA from INSEAD.

I lead architecture and technical decision-making for large-scale cloud and AI systems that must perform under real production constraints. My work spans large-scale data platforms, real-time analytics, and early AI/ML adoption across manufacturing, robotics, and high-tech.

Right now I partner with engineering teams on data modernization and applied AI, taking fuzzy problems and turning them into clear requirements, then shipping systems that hold up under load, failure, and real-world edge cases.

Before Google, I spent ~5 years at AWS as a Senior Solutions Architect where I owned a $40M ARR portfolio. I worked closely with product and engineering teams to modernize legacy stacks, improve reliability, and reduce operational overhead. 

Earlier, I led technical processes and delivery across 20+ engineering and consulting teams at Accenture, Slalom, and IBM, with a focus on building simple, reliable systems aligned to business outcomes.

<div class="nav-section">Recent Posts</div>

{% assign business_posts = site.posts | where_exp: "post",
  "post.categories contains 'strategy'
   or post.categories contains 'business'
   or post.categories contains 'economics'
   or post.categories contains 'branding'
   or post.categories contains 'reflection'
   or post.categories contains 'career'" %}
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
