---
layout: default
title: projects
---

## {{ page.title }}

<ul class="posts">
	{% assign projs = site.projects | sort: 'date' %}
	{% for project in projs reversed %}
		<li><a href="{{ project.url }}" title="{{ project.title }}">{{ project.title }}</a></li>
	{% endfor %}
</ul>