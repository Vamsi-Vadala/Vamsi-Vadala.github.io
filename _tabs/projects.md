---
title: Projects
icon: fas fa-code
order: 2
---

Here are a few projects I’ve worked on:

- **Solo Leveling Tasker** – Android app that blocks distractions until key tasks are done.
- **Instagram Video Downloader** – Automation tool using Selenium.
- **RAG for Scientific Docs** – Biomedical document search system with FAISS + Transformers.

## Detailed Explanations of the above mentioned Projects:

{% assign lc_posts = site.posts | where_exp: "post", "post.categories contains 'Projects'" %}
<ul>
{% for post in lc_posts %}
  <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%b %d, %Y" }}</li>
{% endfor %}
</ul>
