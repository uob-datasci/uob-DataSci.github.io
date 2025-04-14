---
layout: default
title: Events
---

{% assign today = site.time | date: "%Y-%m-%d" %}
{% assign upcoming = site.data.events | where_exp: "e", "e.date >= today" | sort: "date" %}
{% assign past = site.data.events | where_exp: "e", "e.date < today" | sort: "date" | reverse %}

<h2>Upcoming Events</h2>
{% if upcoming.size > 0 %}
  {% for event in upcoming %}

<div class="event">
  <h3>{{ event.title }}</h3>

  {% if event.speaker %}
    <p><strong>Speaker:</strong> {{ event.speaker }}</p>
  {% endif %}

  <p><strong>Date:</strong> {{ event.date | date: "%B %d, %Y" }}</p>
  <p><strong>Time:</strong> {{ event.time }}</p>
  <p><strong>Location:</strong> {{ event.location }}</p>

  {% if event.description %}
    <p>{{ event.description }}</p>
  {% endif %}

  {% if event.abstract %}
    <div class="abstract">
      <strong>Abstract:</strong>
      <p>{{ event.abstract }}</p>
    </div>
  {% endif %}

  {% if event.bio %}
    <div class="bio">
      <strong>Speaker Bio:</strong>
      <p>{{ event.bio }}</p>
    </div>
  {% endif %}
</div>

  {% endfor %}
{% else %}
  <p>No upcoming events.</p>
{% endif %}

<h2>Past Events</h2>
{% for event in past %}

<div class="event">
  <h3>{{ event.title }}</h3>

  {% if event.speaker %}
    <p><strong>Speaker:</strong> {{ event.speaker }}</p>
  {% endif %}

  <p><strong>Date:</strong> {{ event.date | date: "%B %d, %Y" }}</p>
  <p><strong>Time:</strong> {{ event.time }}</p>
  <p><strong>Location:</strong> {{ event.location }}</p>

  {% if event.description %}
    <p>{{ event.description }}</p>
  {% endif %}

  {% if event.abstract %}
    <div class="abstract">
      <strong>Abstract:</strong>
      <p>{{ event.abstract }}</p>
    </div>
  {% endif %}

  {% if event.bio %}
    <div class="bio">
      <strong>Speaker Bio:</strong>
      <p>{{ event.bio }}</p>
    </div>
  {% endif %}
</div>

{% endfor %}
