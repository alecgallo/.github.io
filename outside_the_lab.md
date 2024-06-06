---
layout: default
title: "Outside the lab"
permalink: /outside_the_lab/
---

{% assign outside_lab_posts = site.posts | where: "categories", "outside-the-lab" %}

{% if site.show_excerpts %}
  
  {% for post in outside_lab_posts %}
    <article>
      {% include meta.html post=post preview=true %}
      {{ post.excerpt }}
      <div class="more"><a href="{{ post.url | relative_url }}">read more</a></div>
    </article>
  {% endfor %}
{% else %}
  
  {% for post in outside_lab_posts %}
    <article>
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p>{{ post.date | date: "%B %d, %Y" }}</p>
      {{ post.content }}
    </article>
  {% endfor %}
{% endif %}


Currently under development :)

