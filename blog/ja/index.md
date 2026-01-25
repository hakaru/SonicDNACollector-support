---
layout: article
title: ブログ
lang: ja
---

# ブログ

SonicDNA Collectorの最新ニュース、ヒント、チュートリアルをお届けします。

---

{% assign posts = site.posts_ja | sort: "date" | reverse %}
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
<p><em>まだ投稿がありません。近日公開予定です！</em></p>
{% endif %}

---

[← サポートに戻る](/)
