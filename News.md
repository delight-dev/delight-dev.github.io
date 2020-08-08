---
title: "News"
---

# News

{% for post in site.posts %}
  <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
  <p>{{ post.date | date_to_string }} - {{ post.author }}</p>

  {{ post.content }}
{% endfor %}
