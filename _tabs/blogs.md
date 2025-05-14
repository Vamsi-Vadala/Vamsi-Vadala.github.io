---
title: Blogs
icon: fas fa-pen
order: 5
---

{% assign blog_posts = site.posts | where_exp: "post", "post.tags contains 'blog'" %}
<ul>
{% for post in blog_posts %}
  <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%b %d, %Y" }}</li>
{% endfor %}
</ul>

