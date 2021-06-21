---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

## Working Papers

	{% if post.status != 'published' %}
		{% include archive-single.html %}
	{% endif %}

## Published

{% for post in site.research reversed %}
	{% if post.status == 'published' %}
  		{% include archive-single.html %}
	{% endif %}
{% endfor %}
