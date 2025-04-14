---
title: People
permalink: /people/
---

<div class="container">

<h2>Data Science Research Group</h2>

{% assign people_sorted = site.people | sort: "joined" %}
{% assign people_array = "pi|postdoc|gradstudent|others" | split: "|" %}

{% for item in people_array %}

  <div class="pos_header">
    {% if item == 'postdoc' %}
      <h3>Postdoctoral Research Associates</h3>
    {% elsif item == 'pi' %}
      <h3>Core Faculty</h3>
    {% elsif item == 'gradstudent' %}
      <h3>Doctoral Students</h3>
    {% elsif item == 'visiting' %}
      <h3>Visiting Scholars</h3>
    {% elsif item == 'others' %}
      <h3>Affiliated Faculty</h3>
    {% elsif item == 'alumni' %}
      <h3>Alumni</h3>
    {% endif %}
  </div>

  <div class="people-grid">
    {% for profile in people_sorted %}
      {% if profile.position contains item %}
        <div class="person-card">

          {% if profile.website %}
            {% assign url_tmp = profile.website %}
          {% else %}
            {% assign url_tmp = site.baseurl | append: profile.url %}
          {% endif %}

          {% if profile.avatar %}
            <a href="{{ url_tmp }}">
              <img src="{{ site.baseurl }}/images/people/{{ profile.avatar }}" alt="{{ profile.name }}">
            </a>
          {% else %}
            <a href="{{ url_tmp }}">
              <img src="https://via.placeholder.com/160?text=No+Image" alt="{{ profile.name }}">
            </a>
          {% endif %}

          <a class="name" href="{{ url_tmp }}">{{ profile.name }}</a>

          {% if profile.affiliation %}
            <p class="affiliation">{{ profile.affiliation }}</p>
          {% endif %}

          {% if profile.bio %}
            <p class="bio">{{ profile.bio }}</p>
          {% endif %}

          <div class="social">
            {% if profile.github %}
              <a href="{{ profile.github }}" target="_blank">GitHub</a>
            {% endif %}
            {% if profile.linkedin %}
              <a href="{{ profile.linkedin }}" target="_blank">LinkedIn</a>
            {% endif %}
          </div>
        </div>
      {% endif %}
    {% endfor %}
  </div>
  <hr>
{% endfor %}

<p>List of <a href="/people/alumni">alumni</a>.</p>
</div>

<style>
.container {
  max-width: 1200px;
  margin: auto;
  padding: 2rem;
}

.people-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 2em;
  margin-bottom: 3em;
}

.person-card {
  background: #fff;
  border: 1px solid #e0e0e0;
  padding: 1em;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 2px 6px rgba(0,0,0,0.05);
}

.person-card img {
  width: 200px;
  height: 230px;
  object-fit: cover;
  border-radius: 4px; /* slight rounding if you want, or set to 0 */
  margin-bottom: 0.5em;
}

.person-card .name {
  display: block;
  font-weight: bold;
  margin: 0.5em 0 0.2em;
  font-size: 1.1em;
  color: #005ea5;
  text-decoration: none;
}

.person-card .affiliation {
  font-size: 0.9em;
  color: #666;
}

.bio {
  font-size: 0.9em;
  color: #444;
  margin-top: 0.5em;
}

.social a {
  display: inline-block;
  margin: 0.3em;
  font-size: 0.85em;
  color: #005ea5;
  text-decoration: none;
}

.social a:hover {
  text-decoration: underline;
}
</style>
