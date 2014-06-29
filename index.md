---
layout: page
title: Chris Shireman's Blog
tagline: Supporting tagline
---
{% include JB/setup %}

{% for post in site.posts %}
# [{{post.title}}] ({{ BASE_PATH }}{{post.url}})

{{post.description}} 

[read more] ({{ BASE_PATH }}{{post.url}})

{% endfor %}



