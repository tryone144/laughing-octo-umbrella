---
layout: default  
---

__Revealing Octocats__ allows you to host your [reveal.js](https://revealjs.com) slides with [jekyll](https://jekyllrb.com) on [GitHub Pages](https://pages.github.com/).

# Usage

See the [README]({% link readme.html %}) for more details.

## Demonstration

<!--
{% comment %}
{% assign collection = site.collections | where: "label", "slides" | first %}
{% assign slidespath = collection.relative_directory | remove_first: "_" %}
{% endcomment %}
-->
<!-- deleteme -->
{% capture slidespath %}{% link slides.md %}{% endcapture %}
{% assign slidespath = slidespath | split: "/" %}
{% assign slidespath = slidespath[1] %}
<!-- endof: deleteme -->

[Demo]({% link slides/demo.html %}) using default html syntax.

Small [demo]({% link slides/demo2.md %}) using only inline-markdown.


# Most Recent Slides

{% include slide-list.html limit=2 %}

<a href="{{ slidespath | prepend: site.baseurl }}/">view more</a>

