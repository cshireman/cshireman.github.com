---
layout: page
title: Chris Shireman's Blog
tagline: Supporting tagline
---
{% include JB/setup %}

{% for post in site.posts limit:10 %}
<h2><a href="{{ BASE_PATH }}{{ post.url }}">{{post.title}}</a></h2>

{{post.description}} 

<a href="{{ BASE_PATH }}{{ post.url }}">read more</a>
<br/>
<br/>

{% endfor %}



