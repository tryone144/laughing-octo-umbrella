---
layout: default  
permalink: /slides/index.html  
---

# All Slides

<ul class="post-list">
<!-- Does not work as long as https://github.com/jekyll/jekyll/issues/6209 and https://github.com/jekyll/jekyll/issues/6211 are not fixed -->
{% comment %}
    {% for slide in site.slides %}
    {% endfor %}
{% endcomment %}
    <!-- deleteme -->
    {% for slide in site.pages %}
    {% assign slide_path = slide.path | split:"/" | first %}
    {% if slide.layout == "slide" and slide_path == "slides" %}
    <!-- endof: deleteme -->
        <li>
            <h2><a class="post-link" href="{{ slide.url | prepend: site.baseurl }}">{{ slide.title}}</a></h2>
            <p class="post-description">{{ slide.description }}</p>
        </li>
    {% endif %} <!-- deleteme -->
    {% endfor %}
</ul>
