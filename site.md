---
layout: default
---

🏠

[📁 docs](/docs)  
[📁 posts](/posts)  
[📁 about](/about)  

**Recent Blog Posts:**

{% for post in site.posts %}
📄 [{{ post.date | date_to_string }} {{ post.title }}]({{ post.url }})  
{% endfor %}
