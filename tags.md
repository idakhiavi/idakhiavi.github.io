---
layout: default
title: Tags
description: "Browse Ida's Night Room by topic."
permalink: /tags/
---

<section class="page-intro"><p class="eyebrow">TAG STATION <span lang="ja">トピック</span></p><h1>Browse by signal</h1><p>Pick a frequency and see everything filed under it.</p></section>

{% assign sorted_tags = site.tags | sort %}
{% if sorted_tags and sorted_tags.size > 0 %}
<nav class="tag-index" aria-label="Tag index">{% for tag in sorted_tags %}<a href="#{{ tag[0] | slugify }}">#{{ tag[0] }} <span>{{ tag[1].size }}</span></a>{% endfor %}</nav>
<div class="tag-sections">{% for tag in sorted_tags %}<section class="tag-section" id="{{ tag[0] | slugify }}"><header><h2>#{{ tag[0] }}</h2><span>{{ tag[1].size }} {% if tag[1].size == 1 %}track{% else %}tracks{% endif %}</span></header><ul>{% for post in tag[1] %}<li><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%Y.%m.%d' }}</time><a href="{{ post.url | relative_url }}">{{ post.title }}</a><span aria-hidden="true">▶</span></li>{% endfor %}</ul></section>{% endfor %}</div>
{% else %}<div class="empty-screen"><span aria-hidden="true">#</span><p>No tag frequencies yet.</p></div>{% endif %}
