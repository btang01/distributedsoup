---
layout: default
title: Home
---

# Distributed Soup

Ideas at the intersection of **technology, strategy**, and **innovation**.

---

## Blog Posts
<ul>
  {% for post in site.posts %}
    <li>
      <span>{{ post.date | date: "%d %b %Y" }}</span> »
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

---

## AWS Blog Posts
<ul>
  <li>
    <span>March 3, 2022</span> »
    <a href="https://aws.amazon.com/blogs/security/streamlining-evidence-collection-with-aws-audit-manager/">Streamlining evidence collection with AWS Audit Manager</a>
  </li>
  <li>
    <span>June 29, 2021</span> »
    <a href="https://aws.amazon.com/blogs/architecture/how-banks-can-use-aws-to-meet-compliance/">How Financial Institutions can use AWS to Address Regulatory Reporting</a>
  </li>
</ul>

---

## About Me
Hi, I'm **Brian Tang**, a solutions architect and technologist.
