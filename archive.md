---
layout: default
title: Archive
permalink: /archive/
---

# Archive

{% assign posts_by_month = site.posts | group_by_exp: "post", "post.date | date: '%Y-%m'" | sort: 'name' | reverse %}

{% for month in posts_by_month %}
  {% assign ym = month.name %}
  {% assign label = month.items[0].date | date: '%B %Y' %}
  <h2 id="{{ ym }}">{{ label }}</h2>
  <ul>
    {% for post in month.items %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <span class="meta">{{ post.date | date: "%b %-d, %Y" }}</span>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
