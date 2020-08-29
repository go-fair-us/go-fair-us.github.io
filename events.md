---
layout: page
title: Events
permalink: /events/
feature-img: "assets/img/gofair_background.jpg"
order: 4
---

{% assign sorted = site.events | sort: "date" | reverse %} 
{% for event in sorted %}
  <hr>
  <h3>
    <a href="{{ event.url | prepend: site.baseurl }}">
      {{ event.title }}
    </a>
  </h3>
  <p class="meta">
    <span>{{ event.date | date: "%B %-d, %Y" }}</span>
    {% if event.date2 %}
    <span> - </span>
    <span>{{ event.date2 | date: "%B %-d, %Y" }}</span>
    {% endif %}
  </p>
  <p class="meta">{{ event.location }}</p>
  <p class="excerpt">{{ event.excerpt }}</p>
  <a class="button" href="{{ event.url | relative_url }}">
    {{ site.theme_settings.str_continue_reading }}
  </a>
{% endfor %}
