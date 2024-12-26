---
layout: default
title: "Home"
---

# Welcome to My Tech Blog

Hello world! This is a minimal homepage for my Jekyll-powered tech blog.  
Stay tuned for more posts and updates.


---

## Blog Posts
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>  
      <small>{{ post.date | date: "%B %d, %Y" }}</small>
    </li>
  {% endfor %}
</ul>

---


*Powered by [Jekyll](https://jekyllrb.com)*
