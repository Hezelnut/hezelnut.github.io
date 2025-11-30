---
layout: post
title: "내 블로그 글"
user: "SeungBo, Moon"
---

{% if user %}
  안녕하세요, {{ user.name }}님!
{% endif %}

# {{ page.title }}

작성일: {{ page.date | date: "%Y년 %m월 %d일" }}

{% if page.tags %}
태그: {% for tag in page.tags %}{{ tag }}{% unless forloop.last %}, {% endunless %}{% endfor %}
{% endif %}

## 최근 글 목록

{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date_to_string }}
{% endfor %}
