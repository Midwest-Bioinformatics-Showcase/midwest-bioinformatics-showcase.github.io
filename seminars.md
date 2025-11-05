---
layout: default
title: Seminars
---

# Seminars

## Upcoming

<ul>
{% assign future = site.seminars | where_exp:"s","s.date >= site.time" | sort: "date" %}
{% for seminar in future %}
  <li>
    <a href="{{ seminar.url | relative_url }}"><strong>{{ seminar.title }}</strong></a><br/>
    {{ seminar.speaker }} — {{ seminar.date | date: "%B %d, %Y" }}  
    <em>{{ seminar.location }}</em>
  </li>
{% endfor %}
</ul>

## Past

<ul>
{% assign past = site.seminars | where_exp:"s","s.date < site.time" | sort: "date" | reverse %}
{% for seminar in past %}
  <li>
    <a href="{{ seminar.url | relative_url }}"><strong>{{ seminar.title }}</strong></a><br/>
    {{ seminar.speaker }} — {{ seminar.date | date: "%B %d, %Y" }}
  </li>
{% endfor %}
</ul>
