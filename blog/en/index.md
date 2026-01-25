---
layout: article
title: Blog
lang: en
---

# Blog

Stay updated with the latest news, tips, and tutorials for SonicDNA Collector.

---

{% assign posts = site.posts_en | sort: "date" | reverse %}
{% if posts.size > 0 %}
<ul>
{% for p in posts %}
  <li>
    <strong>{{ p.date | date: "%Y-%m-%d" }}</strong> - 
    <a href="{{ p.url | relative_url }}">{{ p.title }}</a>
  </li>
{% endfor %}
</ul>
{% else %}
<p><em>No posts yet. Check back soon!</em></p>
{% endif %}

---

[← Back to Support](/)
