---
layout: default
title: Seminars
---

# Seminars

## Upcoming

{% assign upcoming = site.seminars | where_exp: "item", "item.date >= site.time" | sort: "date" %}
{% if upcoming.size > 0 %}
<ul>
{% for seminar in upcoming %}
  <li>
    <a href="{{ seminar.url | relative_url }}">{{ seminar.title }}</a><br>
    {{ seminar.speaker }} — {{ seminar.date | date: "%B %d, %Y" }}
  </li>
{% endfor %}
</ul>
{% else %}
<p><em>No upcoming seminars scheduled.</em></p>
{% endif %}

---

## Past

{% assign past = site.seminars | where_exp: "item", "item.date < site.time" | sort: "date" | reverse %}
{% if past.size > 0 %}
<ul>
{% for seminar in past %}
  <li>
    <a href="{{ seminar.url | relative_url }}">{{ seminar.title }}</a><br>
    {{ seminar.speaker }} — {{ seminar.date | date: "%B %d, %Y" }}
  </li>
{% endfor %}
</ul>
{% else %}
<p><em>No past seminars yet.</em></p>
{% endif %}
