---
title: News
layout: post
---
<!-- <div id="primary">
    <h1>News</h1>
    <div id="feed"></div>
</div> -->

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>