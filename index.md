---
layout: default
title: Midwest Bioinformatics Showcase
---

# Midwest Bioinformatics Showcase

Connecting Researchers in Genomics, Data Science, and Computation across the Midwest.

---

## Upcoming Seminars

<ul>
{% for seminar in site.seminars %}
  <li>
    <a href="{{ seminar.url | relative_url }}"><strong>{{ seminar.title }}</strong></a><br/>
    {{ seminar.speaker }} — {{ seminar.date | date: "%B %d, %Y" }}
  </li>
{% endfor %}
</ul>

---

Hosted jointly by [Purdue University](https://purdue.edu) and [Northwestern University](https://www.northwestern.edu/).
