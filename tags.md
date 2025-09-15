---
layout: default
title: Tags
permalink: /tags/
---

# Tags

{% assign tags_raw = '' %}
{% for post in site.posts %}
  {% assign text = post.content | strip_html | replace: ',', ' ' | replace: '.', ' ' | replace: '!', ' ' | replace: '?', ' ' | replace: ';', ' ' | replace: ':', ' ' | replace: ')', ' ' | replace: '(', ' ' %}
  {% assign words = text | split: ' ' %}
  {% for w in words %}
    {% if w and w != '' and w | slice: 0, 1 == '#' %}
      {% assign tag = w | remove: '#' %}
      {% capture tags_raw %}{{ tags_raw }}|{{ tag }}{% endcapture %}
    {% endif %}
  {% endfor %}
{% endfor %}
{% assign tag_list = tags_raw | split: '|' | uniq | sort %}

{% for tag in tag_list %}
  {% if tag != '' %}
    {% assign sigil = '#' | append: tag %}
    <h2 id="{{ tag }}">#{{ tag }}</h2>
    <ul>
      {% for p in site.posts %}
        {% if p.content contains sigil %}
          <li><a href="{{ p.url | relative_url }}">{{ p.title }}</a> <span class="meta">({{ p.date | date: "%b %-d, %Y" }})</span></li>
        {% endif %}
      {% endfor %}
    </ul>
  {% endif %}
{% endfor %}
