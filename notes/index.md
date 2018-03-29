---
layout: default
title: notes
---

## {{ page.title }}

Here are some problems/notes I've written for classes:

<ul class="notes">
	{% assign notes = site.notes | sort: 'date' %}
	{% for note in notes reversed %}
	<li><a href="{{ note.url }}" title="{{ note.title }}">{{ note.title }}</a></li>
	{% endfor %}
</ul>
