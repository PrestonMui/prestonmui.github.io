---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

## Peer-reviewed

{% for post in site.research reversed %}
	{% if post.status == 'published' %}
  		{% include archive-single.html %}
	{% endif %}
{% endfor %}

## Other

{% for post in site.research reversed %}
	{% if post.status == 'other' %}
  		{% include archive-single.html %}
	{% endif %}
{% endfor %}