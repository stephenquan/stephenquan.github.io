---
layout: default
title: "Unix posts"
---

{% for post in site.categories.Unix %}

# [{{post.title}}]({{post.url}})
By {{post.author}} in {{post.categories}}  
<small>{{post.date | date_to_string}}</small>

{{ post.content }}

---

{% endfor %}

