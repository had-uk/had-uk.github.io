---
layout: default
title: Recent Activities
---

# Recent Activities
Here you can find information about our recent activities, including events, workshops, publications, and collaborations. We regularly update this page to keep our community informed about our latest work and initiatives.

{% assign sorted_activities = site.data.activities | sort: "date" | reverse %}
<div class="activities-list">
{% for activity in sorted_activities %}
  {% assign type_slug = activity.type | downcase | replace: " ", "-" %}
  <div class="activity-card type-{{ type_slug }}">
    <div class="activity-body">
      <div class="activity-meta">
        {% if activity.type %}<span class="activity-type">{{ activity.type }}</span>{% endif %}
        {% if activity.location %}<span class="activity-location">{{ activity.location }}</span>{% endif %}
        {% if activity.date %}<span class="activity-date">{{ activity.date }}</span>{% endif %}
      </div>
      <p class="activity-title">
        {% if activity.url %}<a href="{{ activity.url }}">{{ activity.title }}</a>{% else %}{{ activity.title }}{% endif %}
      </p>
      {% if activity.description %}<p class="activity-description">{{ activity.description }}</p>{% endif %}
    </div>
    {% if activity.url %}<a href="{{ activity.url }}" class="activity-link">View {{ activity.type }} &#8594;</a>{% endif %}
  </div>
{% endfor %}
</div>

