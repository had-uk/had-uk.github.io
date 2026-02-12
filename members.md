---
layout: default
title: "Group Members"
hero_title: "Group Members"
hero_description: "Meet the researchers advancing computational approaches in humanities scholarship"
breadcrumb:
  - { text: "Home", url: "/" }
  - { text: "Members", url: "/members", active: true }
---

## Our Research Community

This independent research group brings together scholars from diverse institutions who are pioneering the application of computational methods to humanities research.

<div class="member-grid">
{% assign sorted_members = site.data.members | sort: "name" %}
{% for member in sorted_members %}
  {% if member.url %}
  <a href="{{ member.url }}" class="member-card member-card-link" target="_blank" rel="noopener noreferrer">
    <div class="member-avatar">
      {% if member.image %}
      <img src="{{ member.image }}" alt="{{ member.name }}" class="member-image">
      {% else %}
      <div class="avatar-placeholder" data-name="{{ member.name }}"></div>
      {% endif %}
    </div>
    <h3 class="member-name">{{ member.name }}</h3>
    <p class="member-institution">{{ member.institution }}</p>
  </a>
  {% else %}
  <div class="member-card">
    <div class="member-avatar">
      {% if member.image %}
      <img src="{{ member.image }}" alt="{{ member.name }}" class="member-image">
      {% else %}
      <div class="avatar-placeholder" data-name="{{ member.name }}"></div>
      {% endif %}
    </div>
    <h3 class="member-name">{{ member.name }}</h3>
    <p class="member-institution">{{ member.institution }}</p>
  </div>
  {% endif %}
{% endfor %}
</div>

<script>
// Generate initials for avatar placeholders
document.addEventListener('DOMContentLoaded', function() {
  const placeholders = document.querySelectorAll('.avatar-placeholder[data-name]');
  placeholders.forEach(function(placeholder) {
    const name = placeholder.getAttribute('data-name');
    const initials = name.split(' ')
      .map(word => word.charAt(0).toUpperCase())
      .slice(0, 2)
      .join('');
    placeholder.textContent = initials;
  });
});
</script>