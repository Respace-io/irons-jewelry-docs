---
layout: post
icon: fas fa-scroll
order: 1
toc: true
---
<style>
.table-wrapper {
  --tb-even-bg: #2C2B2B;
  --tb-odd-bg: #2C2B2B;
}
</style>

{% assign sorted_patterns = site.data.pattern_data | sort: 'quality' %}
{% for pattern in sorted_patterns %}
  {% include pattern-card.html %}
{% endfor %}

<!-- buffer for the TOC -->
<div style="height: 800px"></div>



