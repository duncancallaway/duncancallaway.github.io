---
layout: page
title: People
subtitle: 
---

Here is where we'll introduce everyone in EMAC.

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
