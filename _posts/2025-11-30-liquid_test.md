---
tags:
  - Liquid
  - test
user:
  name:"SeungBo Moon"
  age:31
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

```markdown
위 문법의 결과물

user:"SeungBo, Moon" 했는데
user.name은 왜 안나왔지
user: "MSB" 실패


레이아웃 : post << 들어가서 모양이 이상해짐 다른 레이아웃도 시도해볼 것

내 블로그 글
작성일: 2025년 11월 30일

page = 현재 페이지를 명시하는 것 같음
page.date = yyyy-mm-dd-postname.md에서 yyyy-mm-dd 를 가져오는 듯

태그:

{%if%} ~ {%endif%} 문
page.tag가 없어서 성립이 안된 모양임
제일 위에 tag 를 넣어볼까

tag:"Liquid,test" 실패
tag:"Liquid","test" 실패



최근 글 목록
내 블로그 글 - 30 Nov 2025

Test - 29 Nov 2025

{%for post in site.posts limit:5%}
블로그 전체를 가져올 땐 site. 를 쓰나봄
github _posts 에 있는 페이지를 전부 가져올 땐 site.posts
나머진 for문과 비슷해보임 limit:5 추가
```
