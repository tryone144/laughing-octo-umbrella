---
layout: default  
---

RevealTest – host your [reveal.js](https://revealjs.com) slides with [GitHub Pages](https://pages.github.com/) and [jekyll](https://jekyllrb.com).

# HTML Template Demo

[Demo](slides/demo.html) using default html syntax.

# Markdown-only Demo

Small [demo](slides/demo2.html) using only inline-markdown.

<!-- Does not work as long as https://github.com/jekyll/jekyll/issues/6209 and https://github.com/jekyll/jekyll/issues/6211 are not fixed -->
{% comment %}{% if site.slides.size > 0 %}{% endif %}{% endcomment %}
<!-- deleteme -->
{% assign slidescount = 0 %}
{% for slide in site.pages %}
    {% assign slide_path = slide.path | split:"/" | first %}
    {% if slide.layout == "slide" and slide_path == "slides" %}
        {% assign slidescount = slidescount | plus:1 %}
    {% endif %}
{% endfor %}
{% if slidescount > 0 %}
<!-- endof: deleteme -->
# Most Recent Slides

<ul class="post-list">
<!-- Does not work as long as https://github.com/jekyll/jekyll/issues/6209 and https://github.com/jekyll/jekyll/issues/6211 are not fixed -->
{% comment %}
    {% for slide in site.slides limit:5 %}
    {% endfor %}
{% endcomment %}
    <!-- deleteme -->
    {% assign output_count = 0 %}
    {% for slide in site.pages %}
    {% if output_count >= 5 %}
        {% break %}
    {% endif %}
    {% assign slide_path = slide.path | split:"/" | first %}
    {% if slide.layout == "slide" and slide_path == "slides" %}
    {% assign output_count = output_count | plus:1 %}
    <!-- endof: deleteme -->
        <li>
            <h2><a class="post-link" href="{{ slide.url | prepend: site.baseurl }}">{{ slide.title}}</a></h2>
            <p class="post-description">{{ slide.description }}</p>
        </li>
    {% endif %} <!-- deleteme -->
    {% endfor %}
</ul>

{% comment %}
{% assign collection = site.collections | where: "label", "slides" | first %}
{% assign rel_path = collection.relative_directory | remove_first:"_" %}
{% endcomment %}
{% assign rel_path = "slides" %} <!-- deleteme -->
<a href="{{ rel_path }}/">view more</a>
{% endif %}

