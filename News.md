---
title: "News"
---

# News

<ul class="entries">
  {% for post in paginator.posts %}
  <li>
    <h1>{{ post.title }}</h1>
    <p>{{ post.date | date_to_string }} - {{ post.author }}</p>

    {{ post.content }}
  </li>
  {% endfor %}
</ul>


{% include recent-posts.html %}
