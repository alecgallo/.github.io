---
layout: default
title: "Research"
permalink: /research/
---

{% assign research_posts = site.posts | where: "categories", "research" %}

{% if site.show_excerpts %}
  <h2>Past Projects</h2>
  {% for post in research_posts %}
    <article>
      {% include meta.html post=post preview=true %}
      {{ post.excerpt }}
      <div class="more"><a href="{{ post.url | relative_url }}">read more</a></div>
    </article>
  {% endfor %}
{% else %}
  <h2>Past Projects</h2>
  {% for post in research_posts %}
    <article>
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p>{{ post.date | date: "%B %d, %Y" }}</p>
      {{ post.content }}
    </article>
  {% endfor %}
{% endif %}
