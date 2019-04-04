---
title: Blog
layout: post
---
<!-- <div id="primary">
    <h1>News</h1>
    <div id="feed"></div>
</div> -->

<div class="primary">
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">
      <h4>{{ post.title }}</h4>
      </a>
    </li>
  {% endfor %}
</ul>
</div>