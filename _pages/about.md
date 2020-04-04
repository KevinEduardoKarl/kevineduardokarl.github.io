---
layout: archive
title: "About"
permalink: /about/
author_profile: true
header:
  image: "/images/trees.jpg"
---

  I'm a senior data scientist who excels at machine learning, exploratory
  analysis, and data visualizations.


  {% include base_path %}
  {% include group-by-array collection=site.posts field="tags" %}

  {% for tag in group_names %}
    {% assign posts = group_items[forloop.index0] %}
    <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
    {% for post in posts %}
      {% include archive-single.html %}
    {% endfor %}
  {% endfor %}
