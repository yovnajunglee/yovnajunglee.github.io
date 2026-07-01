---
layout: default
title: Other
permalink: /other/
---

<h2>life outside of academia on film</h2>

<div class="gallery">
  {% for photo in site.data.photography %}
  <figure class="gallery-item">
    <img src="{{ photo.src | relative_url }}" alt="{{ photo.caption | default: 'Photograph' }}" loading="lazy">
    {% if photo.caption %}<figcaption>{{ photo.caption }}</figcaption>{% endif %}
  </figure>
  {% endfor %}
</div>