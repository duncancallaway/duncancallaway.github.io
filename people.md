---
layout: page
title: People
subtitle: 
---

Here is where we'll introduce everyone in EMAC.

## Students

<div class="student-grid">
  {% assign students = site.students | sort: 'title' %}
  {% for student in students %}
    {% include student-card.html student=student %}
  {% endfor %}
  {% if students == empty %}
    <p>No students listed yet. Add Markdown files under <code>_students/</code>.</p>
  {% endif %}
</div>
