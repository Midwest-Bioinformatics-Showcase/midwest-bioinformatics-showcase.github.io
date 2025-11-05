---
layout: default
title: Seminars
---

# Seminars

Below are the upcoming and past seminars from the Midwest Bioinformatics Showcase series.

---

## 🗓️ Upcoming Seminars

<table>
  <tr>
    <th>Title</th>
    <th>Speaker</th>
    <th>Date</th>
    <th>Location</th>
  </tr>
  {% assign future = site.seminars | where_exp: "s", "s.date >= site.time" | sort: "date" %}
  {% for seminar in future %}
  <tr>
    <td><a href="{{ seminar.url | relative_url }}">{{ seminar.title }}</a></td>
    <td>{{ seminar.speaker }}</td>
    <td>{{ seminar.date | date: "%B %d, %Y" }}</td>
    <td>{{ seminar.location }}</td>
  </tr>
  {% endfor %}
  {% if future == empty %}
  <tr><td colspan="4"><em>No upcoming seminars scheduled.</em></td></tr>
  {% endif %}
</table>

---

## 📚 Past Seminars

<table>
  <tr>
    <th>Title</th>
    <th>Speaker</th>
    <th>Date</th>
    <th>Location</th>
  </tr>
  {% assign past = site.seminars | where_exp: "s", "s.date < site.time" | sort: "date" | reverse %}
  {% for seminar in past %}
  <tr>
    <td><a href="{{ seminar.url | relative_url }}">{{ seminar.title }}</a></td>
    <td>{{ seminar.speaker }}</td>
    <td>{{ seminar.date | date: "%B %d, %Y" }}</td>
    <td>{{ seminar.location }}</td>
  </tr>
  {% endfor %}
  {% if past == empty %}
  <tr><td colspan="4"><em>No past seminars yet.</em></td></tr>
  {% endif %}
</table>
