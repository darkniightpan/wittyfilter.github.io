---
layout: page
title: Hello World!
tagline: Welcome
---
{% include JB/setup %}

    希望越大，失望越大。所以凡事看开，知足常乐。
    能力越大，责任越大。所以不断学习，勇于承担。

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

