---
layout: page
title: other interests
permalink: /other-interests/
description: A growing collection of my other interests.
nav: true
nav_order: 3
#display_categories: [work, fun]
horizontal: false
---
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-WR8SYBZP76"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-WR8SYBZP76');
</script>

<!-- pages/other.md -->
<div class="others">
{% if site.enable_other_categories and page.display_categories %}
  <!-- Display categorized others -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_others = site.others | where: "category", category %}
  {% assign sorted_others = categorized_others | sort: "importance" %}
  <!-- Generate cards for each others -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_others %}
      {% include other_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_others %}
      {% include other.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display others without categories -->

{% assign sorted_others = site.others | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_others %}
      {% include other_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_others %}
      {% include other.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
