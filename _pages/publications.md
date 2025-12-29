---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

<h2>Conference Publications</h2>
{% assign conference_pubs = site.publications | where: "category", "conference" | sort: "date" | reverse %}
{% for post in conference_pubs %}
  {% include archive-single-publication.html %}
{% endfor %}

<br />

<h2>Journal Publications</h2>
{% assign journal_pubs = site.publications | where: "category", "journal" | sort: "date" | reverse %}
{% for post in journal_pubs %}
  {% include archive-single-publication.html %}
{% endfor %}

<br />

<h2>Workshop Papers</h2>
{% assign workshop_pubs = site.publications | where: "category", "workshop" | sort: "date" | reverse %}
{% for post in workshop_pubs %}
  {% include archive-single-publication.html %}
{% endfor %}

<br />

<h2>Preprints</h2>
{% assign preprint_pubs = site.publications | where: "category", "preprint" | sort: "date" | reverse %}
{% for post in preprint_pubs %}
  {% include archive-single-publication.html %}
{% endfor %}
