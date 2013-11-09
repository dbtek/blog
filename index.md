---
layout: page
---
{% include JB/setup %}

{% for post in site.posts %}
<article>
<span class="post-date">
{% assign d = post.date | date: "%d" | plus:'0' %}
{{ post.date | date: "%B" }} 
{% case d %}
  {% when 1 or 21 or 31 %}{{ d }}st,
  {% when 2 or 22 %}{{ d }}nd,
  {% when 3 or 23 %}{{ d }}rd,
  {% else %}{{ d }}th,
{% endcase %}
{{ post.date | date: "%Y" }}
</span>
<h3>
	<a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
</h3>
<p>
<a href="{{post.url }}">
{{ if post.shortinfo }}{{ post.shortinfo }}{{ else }}...{{ /if }}
</a>
</p>
</article>
{% endfor %}
