---
layout: page
title: News
permalink: /news/
feature-img: "assets/img/gofair_background.jpg"
order: 3
---

{% assign sorted = site.news | sort: "date" | reverse %}
{% for news in sorted %}
  <hr>
  <h3>
    <a href="{{ news.url | prepend: site.baseurl }}">
      {{ news.title }}
    </a>
  </h3>
  <p class="meta">{{ news.date | date: "%B %-d, %Y" }}</p>
  <p class="excerpt">{{ news.excerpt }}</p>
  <a class="button" href="{{ news.url | relative_url }}">
    {{ site.theme_settings.str_continue_reading }}
  </a>
{% endfor %}
