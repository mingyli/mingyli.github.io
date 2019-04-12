---
title: notes
---

# {{ page.title }}

Here are some miscellaneous problems and notes I've written in the past:

<ul>
	<!-- {% assign notes = site.notes | sort: 'date' %} -->
	{% for post in site.posts %}
        <li>
            <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
        </li>
	{% endfor %}
</ul>
