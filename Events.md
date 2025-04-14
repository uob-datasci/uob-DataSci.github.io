---
layout: default
title: Events
---

{% assign today = site.time | date: "%Y-%m-%d" %}
{% assign upcoming = site.data.events | where_exp: "e", "e.date >= today" | sort: "date" %}
{% assign past = site.data.events | where_exp: "e", "e.date < today" | sort: "date" | reverse %}
<div class="events-container">


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
</div> <!-- end .events-container -->


<style>
.events-container {
  padding: 2rem;
  max-width: 960px;
  margin: auto;
}

.event {
  background: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 1em;
  margin: 2em 0;
  box-shadow: 2px 2px 8px rgba(0,0,0,0.05);
}

.event h3 {
  margin-top: 0;
}

.event p {
  margin: 0.5em 0;
}
</style>

