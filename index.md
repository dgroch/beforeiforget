---
layout: default
title: Home
---

<div class="home">
  <h1 class="page-heading">Dispatches</h1>
  
  <p class="site-description">{{ site.description }}</p>

  <p class="reading-note"><em>New here? Start at the top — the dispatches build on each other. They are presented in the order they were written.</em></p>
  
  <ul class="post-list">
    {% assign sorted_dispatches = site.dispatches | sort: 'dispatch_number' %}
    {% for dispatch in sorted_dispatches %}
      <li>
        <span class="post-meta">
          {% if dispatch.dispatch_number %}No. {{ dispatch.dispatch_number }} &mdash; {% endif %}{{ dispatch.date | date: "%B %d, %Y" }}
        </span>
        <h3>
          <a class="post-link" href="{{ dispatch.url | relative_url }}">{{ dispatch.title }}</a>
        </h3>
        {% if dispatch.subtitle %}
          <p class="post-subtitle">{{ dispatch.subtitle }}</p>
        {% endif %}
      </li>
    {% endfor %}
  </ul>

  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | relative_url }}">via RSS</a></p>
</div>
