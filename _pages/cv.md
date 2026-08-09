---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* Ph.D., Durham University — placeholder, add year/details
* [Add earlier degrees here]

Work experience
======
* IFAE — Postdoctoral Researcher (current) — placeholder, add dates/details
* Rice University — Postdoctoral Researcher — placeholder, add dates/details
* Durham University — Postdoctoral Researcher — placeholder, add dates/details

Skills
======
* Placeholder — add your skills here

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>

Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Service and leadership
======
* Placeholder — add service/leadership roles here
