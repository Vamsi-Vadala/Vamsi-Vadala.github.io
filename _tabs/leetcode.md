---
title: LeetCode
icon: fas fa-lightbulb
order: 4
---

{% assign lc_posts = site.posts | where_exp: "post", "post.categories contains 'LeetCode'" %}
<ul>
{% for post in lc_posts %}
  <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%b %d, %Y" }}</li>
{% endfor %}
</ul>

