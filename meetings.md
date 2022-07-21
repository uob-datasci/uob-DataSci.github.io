---
title: Meetings
permalink: /meetings/
---

### <span style="color:#2348a3">MaVi Seminar Series</span>
<br>
<div class="content list">
  {% for post in site.posts %}
    {% if post.categories contains 'meeting' %}
    <div class="list-item">
    <p class="list-post-title">
        <small>{{post.date | date: "%d/%m/%y" }} {{ post.time }}</small>: <b><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></b>
        {{post.content}}
        </p>
    </div>
    {% endif %}
  {% endfor %}
</div>


#### Other relevant meetings:


<hr>
{% include footer.html %}