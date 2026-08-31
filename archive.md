---
layout: default
title: Archive
description: "Every post from Ida's Corner, newest first."
permalink: /archive/
---

<section class="page-intro"><p class="eyebrow">THE INDEX</p><h1>Archive</h1><p>Every post, newest first.</p></section>

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
<div class="archive-catalogue">
{% for year in posts_by_year %}
  <section class="archive-year">
    <div class="archive-year-label"><span>{{ year.name }}</span><small>{{ year.items.size }} POSTS</small></div>
    <ol class="archive-list">{% for post in year.items %}<li><span class="archive-index" aria-hidden="true">{% if forloop.index < 10 %}0{% endif %}{{ forloop.index }}</span><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%b %d' }}</time><a href="{{ post.url | relative_url }}">{{ post.title }}</a><span class="archive-play" aria-hidden="true">→</span></li>{% endfor %}</ol>
  </section>
{% endfor %}
</div>
