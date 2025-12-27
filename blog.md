---
layout: default
title: Blog
permalink: /blog/
---

<h1>Blog</h1>

<div>
  {% for post in site.posts %}
    <article style="margin-bottom: 2rem; text-align: center;">
      <p><a href="{{ post.url | relative_url }}">{{ post.title }}</a></p>
      <small>{{ post.date | date: "%B %d, %Y" }}</small>

      {% if post.image %}
          <div style="margin-top: 0.5rem;">
            <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" style="max-width: 50%; height: auto; border-radius: 8px;">
          </div>
      {% endif %}

      {% if post.caption %}
        <div style="margin-top: 0.5rem; font-style: italic;">
          {{ post.caption | markdownify }}
        </div>
      {% endif %}

      <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>

      {% if post.content contains '```' %}
        <div style="background-color: #f5f5f5; padding: 1rem; border-radius: 5px; overflow-x: auto;">
          {{ post.content | markdownify }}
        </div>
      {% endif %}
    </article>
  {% endfor %}
</div>
