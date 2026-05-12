---
layout: page
permalink: /research/
title: research
years: [2026, 2025, 2024, 2023, 2022, 2019, 2018, 2017, 2016]
nav: true
nav_order: 1
---

<div class="publications">

{% for y in page.years %}
  <div class="year-section">
    <div class="year"><strong>{{y}}</strong></div>
    <div class="year-papers">
      {% bibliography -f papers -q @*[year={{y}}]* %}
    </div>
  </div>
{% endfor %}
</div>

