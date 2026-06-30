---
layout: default
title: CV
permalink: /cv/
---

<h1>Curriculum Vitae</h1>
<p><a href="{{ '/assets/cv.pdf' | relative_url }}">Download as PDF →</a></p>

<h2>Education</h2>
{% for entry in site.data.cv.education %}
<div class="cv-entry">
  <div class="cv-entry-date">{{ entry.date }}</div>
  <div>
    <div class="cv-entry-title">{{ entry.title }}</div>
    <div class="cv-entry-org">{{ entry.org }}</div>
    {% if entry.detail and entry.detail != "" %}<div class="cv-entry-detail">{{ entry.detail }}</div>{% endif %}
  </div>
</div>
{% endfor %}

<h2>Publications</h2>
<ul class="pub-list">
  {% for pub in site.data.publications %}
  <li class="pub-card">
    <div class="pub-tab{% if pub.type == 'conference' %} is-conference{% elsif pub.type == 'preprint' %} is-preprint{% endif %}"></div>
    <div class="pub-body">
      <div class="pub-meta"><span class="pub-year">{{ pub.year }}</span> &nbsp;·&nbsp; {{ pub.type | capitalize }}</div>
      <p class="pub-title">{{ pub.title }}</p>
      <p class="pub-authors">{{ pub.authors | markdownify | remove: "<p>" | remove: "</p>" }}</p>
      <p class="pub-authors" style="margin-top:-0.3rem; color: var(--color-ink-soft); font-style: italic;">{{ pub.venue }}</p>
      <div class="pub-links">
        {% for link in pub.links %}<a href="{{ link.url }}">{{ link.label }}</a>{% endfor %}
      </div>
    </div>
  </li>
  {% endfor %}
</ul>

<h2>Experience</h2>
{% for entry in site.data.cv.experience %}
<div class="cv-entry">
  <div class="cv-entry-date">{{ entry.date }}</div>
  <div>
    <div class="cv-entry-title">{{ entry.title }}</div>
    <div class="cv-entry-org">{{ entry.org }}</div>
    {% if entry.detail and entry.detail != "" %}<div class="cv-entry-detail">{{ entry.detail }}</div>{% endif %}
  </div>
</div>
{% endfor %}

<h2>Awards</h2>
{% for entry in site.data.cv.awards %}
<div class="cv-entry">
  <div class="cv-entry-date">{{ entry.date }}</div>
  <div>
    <div class="cv-entry-title">{{ entry.title }}</div>
    {% if entry.org and entry.org != "" %}<div class="cv-entry-org">{{ entry.org }}</div>{% endif %}
  </div>
</div>
{% endfor %}
