---
layout: post
icon: fas fa-book
order: 2
toc: true
---
{% assign sorted = site.data.spellbook_data | sort: 'name'%}
{% for recipe in sorted %}
  {% assign desc = "" | append: site.data.spellbook_descriptions[recipe.id].description %}
  {% include crafting-table-card.html pixelated="true" desc=desc%}
{% endfor %}

<!-- buffer for the TOC -->
<div style="height: 800px"></div>

