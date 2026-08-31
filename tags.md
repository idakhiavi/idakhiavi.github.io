---
layout: default
title: Topics
description: "Browse Ida's Corner by subject."
permalink: /tags/
---

<section class="page-intro"><p class="eyebrow">TOPIC INDEX</p><h1>Browse by subject</h1><p>Writing grouped by the ideas it returns to.</p></section>

{% assign sorted_tags = site.tags | sort %}
{% if sorted_tags and sorted_tags.size > 0 %}
<nav class="tag-index" aria-label="Tag index">{% for tag in sorted_tags %}<a href="#{{ tag[0] | slugify }}">#{{ tag[0] }} <span>{{ tag[1].size }}</span></a>{% endfor %}</nav>
<div class="tag-sections">{% for tag in sorted_tags %}<section class="tag-section" id="{{ tag[0] | slugify }}"><header><h2>#{{ tag[0] }}</h2><span>{{ tag[1].size }} {% if tag[1].size == 1 %}post{% else %}posts{% endif %}</span></header><ul>{% for post in tag[1] %}<li><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%Y.%m.%d' }}</time><a href="{{ post.url | relative_url }}">{{ post.title }}</a><span aria-hidden="true">→</span></li>{% endfor %}</ul></section>{% endfor %}</div>
{% else %}<div class="empty-screen"><span aria-hidden="true">#</span><p>No topics yet.</p></div>{% endif %}
