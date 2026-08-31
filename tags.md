---
layout: default
title: Tags
permalink: /tags/
---

# Tags

{% assign tags_raw = '' %}
{% for post in site.posts -%}
  {% assign segments = post.content | strip_html | split: '#' %}
  {% for s in segments offset:1 -%}
    {% if s and s != '' and s | slice: 0, 1 != ' ' -%}
      {% assign token = s | strip | split: ' ' | first %}
      {% assign token = token | replace: ',', '' | replace: '.', '' | replace: '!', '' | replace: '?', '' | replace: ';', '' | replace: ':', '' | replace: ')', '' | replace: '(', '' | replace: ']', '' | replace: '[', '' | replace: '"', '' | replace: "'", '' %}
      {% if token != '' -%}
        {% capture tags_raw %}{{ tags_raw }}|{{ token }}{% endcapture %}
      {% endif -%}
    {% endif -%}
  {% endfor -%}
{% endfor -%}
{% assign tag_list = tags_raw | split: '|' | uniq | sort %}

{% for tag in tag_list -%}
{% if tag != '' -%}
<section class="tag-section" id="{{ tag }}">
  <h2>#{{ tag }}</h2>
  <ul>
{%- for p in site.posts -%}
  {% assign found = '' %}
  {% assign segs = p.content | strip_html | split: '#' %}
  {% for z in segs offset:1 -%}
    {% if z and z != '' and z | slice: 0, 1 != ' ' -%}
      {% assign tok = z | strip | split: ' ' | first %}
      {% assign tok = tok | replace: ',', '' | replace: '.', '' | replace: '!', '' | replace: '?', '' | replace: ';', '' | replace: ':', '' | replace: ')', '' | replace: '(', '' | replace: ']', '' | replace: '[', '' | replace: '"', '' | replace: "'", '' %}
      {% if tok == tag -%}
        {% assign found = '1' %}
      {% endif -%}
    {% endif -%}
  {% endfor -%}
  {% if found != '' -%}
    <li><a href="{{ p.url | relative_url }}">{{ p.title }}</a></li>
  {% endif -%}
{%- endfor -%}
  </ul>
</section>
{% endif -%}
{% endfor -%}
