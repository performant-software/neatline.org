---
title: News
author: admin
layout: page
---

{% for post in site.posts %}
<header>
    <p class="kicker">{{ post.date | date_to_string }}</p>
    <h1><a href="{{ post.url | prepend: site.url }}">{{ post.title }}</a></h1>
</header>
<div class="entry">
    {{ post.excerpt }}
</div>
{% endfor %}
