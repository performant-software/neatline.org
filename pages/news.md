---
title: News
layout: page
permalink: /news/
---
<div class="primary case">
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.date | date: "%m/%d/%Y" }} | {{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
</div>