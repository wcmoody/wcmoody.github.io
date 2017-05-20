---
layout: page
title: Blog
permalink: /blog/
---

Here are some of my blogs from CTF write-up and other things of interest to me.

  <h1 class="page-heading">Posts</h1>
  
  <ul class="post-list">
    {% for post in site.posts %}
      <li>
        {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
        <span class="post-meta">{{ post.date | date: date_format }}</span>

        <h2>
          <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </h2>

	{{ post.excerpt }} <a href="{{ post.url }}">Read more &raquo;</a>
      </li>
    {% endfor %}
  </ul>


