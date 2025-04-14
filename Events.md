---
title: Events
permalink: /events/
---

### <span style="color:#0095a9">Data Science Seminar Series</span>
<br>
<div class="content list">
  {% for post in site.posts %}
    {% if post.categories contains 'event' %}
    <div class="list-item">
    <p class="list-post-title">
        <small>{{post.date | date: "%d/%m/%y" }} {{ post.time }} Room: {{ post.location }}</small>: <b><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></b>
        {{post.content}}
        </p>
    </div>
    {% endif %}
  {% endfor %}
</div>


#### Other relevant Events:


<hr>
{% include footer.html %}