---
layout: default
title: Blog
---

# 📝 Veny Blog

Welcome to the official blog of the Veny Language. Here we explore object-oriented methodology, language design, domain modeling, and Veny's role in the OO ecosystem.

---

{% for post in site.posts %}
### [{{ post.title }}]({{ post.url }})
🗓️ {{ post.date | date: "%Y-%m-%d" }}

{{ post.excerpt | strip_html | truncatewords: 30 }}

[Read more →]({{ post.url }})

---

{% endfor %}
