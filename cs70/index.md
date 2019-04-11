---
title: cs70
---

# notes for cs70

Here are notes I wrote for when I TAed
[CS70: Discrete Mathematics and Probability Theory](http://eecs70.org).
My Dropbox Paper presentations can be found [here][dropbox-paper].

<ul>
	{% for note in site.cs70 %}
        <li>
            <a href="{{ note.url }}" title="{{ note.title }}">{{ note.title }}</a>: {{ note.topic }}
        </li>
	{% endfor %}
</ul>

<!-- {% assign notes = site.notes | sort: 'date' %} -->
<!-- {% for note in site.cs70 %}
- [{{note.title}}]({{note.url}}): {{note.topic}}
{% endfor %} -->

[dropbox-paper]: https://paper.dropbox.com/doc/Directory--Aa8zn3NZUNZZP~Da2Enjg4bcAQ-kbOP14lGGBsqWduzjqez3
