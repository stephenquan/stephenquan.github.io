---
layout: default
---

[🏠](/)
/ posts

{% for category in site.categories %}
  **{{ category[0] }} Blog Posts**
  {% for post in category[1] %}
📄 [{{ post.date | date_to_string }} {{ post.title }}]({{ post.url }})  
  {% endfor %}
{% endfor %}

