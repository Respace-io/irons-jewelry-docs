---
layout: post
icon: fa-solid fa-coins
order: 3
toc: true
---

<style>
.table-wrapper {
  --tb-even-bg: #2C2B2B;
  --tb-odd-bg: #2C2B2B;
}
</style>
{% assign sorted = site.data.material_data | sort: 'quality'%}
{% assign groups = site.data.material_data | group_by: 'types'%}
{% for group in groups %}
  <h2 id="{{group.name}}"> {{group.name}}</h2>
  <hr>

{% assign sorted_items = group.items | sort: 'sort' %}

  {% for pattern in sorted_items %}
  {% include material-card.html %}
  {% endfor %}
{% endfor %}



<!-- buffer for the TOC -->
<div style="height: 800px"></div>
