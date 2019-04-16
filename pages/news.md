---
title: News
layout: page
permalink: /news/
---
<div class="primary">
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}"><h4>{{ post.title }}</h4></a>
    </li>
  {% endfor %}
</ul>
</div>