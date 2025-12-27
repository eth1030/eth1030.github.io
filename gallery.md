---
layout: default
title: "Photo Blog"
permalink: /photos/
---
<h1>Photo Blog</h1>

<ul style="list-style: none; padding: 0;">
  {% for post in site.posts %}
    <li style="display: inline-block; margin: 0.5rem; text-align: center;">
      <a href="{{ post.url | relative_url }}">
        <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" style="width: 150px; height: auto; border-radius: 4px;">
      </a>
      <p style="font-size: 0.8rem;">{{ post.caption }}</p>
    </li>
  {% endfor %}
</ul>
