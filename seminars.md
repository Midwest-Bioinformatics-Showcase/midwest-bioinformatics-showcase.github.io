---
layout: default
title: Seminars
---

# Seminars

Welcome to the seminar schedule. Each seminar includes its abstract page, Zoom link, calendar invite, and (when available) a recording.

---

## Upcoming Seminars

{% assign upcoming = site.seminars | where_exp: "s", "s.date >= site.time" | sort: "date" %}
{% if upcoming.size > 0 %}

<table class="seminar-table">
  <thead>
    <tr>
      <th>Date</th>
      <th>Title & Speaker</th>
      <th>Details</th>
    </tr>
  </thead>
  <tbody>
  {% for talk in upcoming %}
    <tr>
      <td class="seminar-date">{{ talk.date | date: "%b %-d, %Y" }}</td>
      <td>
        <a href="{{ talk.url | relative_url }}" class="seminar-title">{{ talk.title }}</a><br>
        <span class="seminar-speaker">{{ talk.speaker }}</span>
      </td>
      <td class="seminar-links">
        {% if talk.zoom_link %}
        <a href="{{ talk.zoom_link }}" class="button small">Join Zoom</a><br>
        {% endif %}
        {% if talk.calendar_link %}
        <a href="{{ talk.calendar_link }}" class="text-link">Add to Calendar</a><br>
        {% endif %}
        {% if talk.recording_link %}
        <a href="{{ talk.recording_link }}" class="text-link">Recording</a>
        {% endif %}
      </td>
    </tr>
  {% endfor %}
  </tbody>
</table>

{% else %}
<p><em>No upcoming seminars scheduled.</em></p>
{% endif %}

---

## Past Seminars

{% assign past = site.seminars | where_exp: "s", "s.date < site.time" | sort: "date" | reverse %}
{% if past.size > 0 %}

<table class="seminar-table">
  <thead>
    <tr>
      <th>Date</th>
      <th>Title & Speaker</th>
      <th>Recording</th>
    </tr>
  </thead>
  <tbody>
  {% for talk in past %}
    <tr>
      <td class="seminar-date">{{ talk.date | date: "%b %-d, %Y" }}</td>
      <td>
        <a href="{{ talk.url | relative_url }}" class="seminar-title">{{ talk.title }}</a><br>
        <span class="seminar-speaker">{{ talk.speaker }}</span>
      </td>
      <td class="seminar-links">
        {% if talk.recording_link %}
          <a href="{{ talk.recording_link }}" class="text-link">Watch</a>
        {% else %}
          <span class="muted">Not available</span>
        {% endif %}
      </td>
    </tr>
  {% endfor %}
  </tbody>
</table>

{% else %}
<p><em>No past seminars yet.</em></p>
{% endif %}
