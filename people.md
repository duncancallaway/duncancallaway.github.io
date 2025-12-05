---
layout: page
title: People
subtitle: 
---

EMAC (Energy, Modeling, Analysis and Controls) is led by Duncan Callaway. Learn more on his UC Berkeley profile.

<div class="student-profile">
  <div class="student-header">
    <img class="student-photo" src="/assets/img/headshot_small_23.png" alt="Duncan Callaway" />
    <div class="student-meta">
      <h2 class="student-name">Duncan Callaway</h2>
      <div class="student-role">EMAC Lab Lead</div>
      <div class="student-links">
        <a href="https://vcresearch.berkeley.edu/faculty/duncan-callaway" target="_blank" rel="noopener">UC Berkeley profile</a>
      </div>
    </div>
  </div>
</div>

## Students

<div class="student-grid">
  {% assign sorted = site.students | sort: 'title' %}
  {% for student in sorted %}
    {% unless student.alumni %}
      {% include student-card.html student=student %}
    {% endunless %}
  {% endfor %}
</div>

{% assign alumni = site.students | where: 'alumni', true | sort: 'title' %}
{% if alumni and alumni.size > 0 %}
## Alumni

<div class="student-grid">
  {% for student in alumni %}
    {% include student-card.html student=student %}
  {% endfor %}
</div>
{% endif %}
