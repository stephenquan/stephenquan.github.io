---
layout: default
---

{% for post in site.posts %}

# [{{post.title}}](/posts/{{post.categories}}#{{post.id}})
By {{post.author}} in [{{post.categories}}](/posts/{{post.categories}})
<small>{{post.date | date_to_string}}</small>

{{ post.content }}

---

{% endfor %}

{{ post.content }}
