---
layout: default
title: 存档
---

# 存档

查看所有博客

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%Y 年 %-m 月'" %}
{% for yearMonth in postsByYearMonth %}
  <h2>{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
      <li><a href="{{ post.url }}" style="text-decoration: none; color: #495057" >{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
