---
layout: default
title: "Home"
---

# Welcome to My Tech Blog

Hello world! This is a minimal homepage for my Jekyll-powered tech blog.  
Stay tuned for more posts and updates.

---

{% if site.posts.size > 0 %}
## Recent Posts

{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url | relative_url }})  
  <small>Posted on {{ post.date | date: "%B %d, %Y" }}</small>
{% endfor %}

[View all posts](/blog)
{% else %}
No posts yet—check back soon!
{% endif %}

---

*Powered by [Jekyll](https://jekyllrb.com)*
