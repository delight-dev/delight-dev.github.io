---
title: "News"
---

# News

<ul class="entries">
  {% for post in site.posts %}
  <li>
    <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>

  </li>
  {% endfor %}
</ul>


{% include recent-posts.html %}
