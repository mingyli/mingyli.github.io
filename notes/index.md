---
layout: tufte
title: notes
---

# {{ page.title }}

Here are some miscellaneous problems and notes I've written in the past:

<ul>
	{% assign notes = site.notes | sort: 'date' %}
	{% for note in notes reversed %}
        <li>
            <a href="{{ note.url }}" title="{{ note.title }}">{{ note.title }}</a>
        </li>
	{% endfor %}
</ul>