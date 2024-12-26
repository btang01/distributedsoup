---
layout: default
title: "Blog"
permalink: /blog/
---

# All Posts

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url | relative_url }})
  <small>Posted on {{ post.date | date: "%B %d, %Y" }}</small>
{% endfor %}
