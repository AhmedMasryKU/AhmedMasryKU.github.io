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

{% comment %} Get all publications and group by year {% endcomment %}
{% assign all_pubs = site.publications | sort: "date" | reverse %}
{% assign years = all_pubs | group_by_exp: "pub", "pub.date | date: '%Y'" | sort: "name" | reverse %}

{% comment %} Table of Contents {% endcomment %}
<div class="publications-toc">
  <h2>Table of Contents</h2>
  <ul>
    {% for year_group in years %}
      <li><a href="#year-{{ year_group.name }}">{{ year_group.name }}</a></li>
    {% endfor %}
  </ul>
</div>

<hr style="margin: 2em 0;" />

{% comment %} Display publications grouped by year {% endcomment %}
{% for year_group in years %}
  <h2 id="year-{{ year_group.name }}" class="publication-year-header">{{ year_group.name }}</h2>
  
  {% comment %} Conference Publications for this year {% endcomment %}
  {% assign year_conference = year_group.items | where: "category", "conference" %}
  {% if year_conference.size > 0 %}
    <h3 class="publication-category-header">Conference Publications</h3>
    {% for post in year_conference %}
      {% include archive-single-publication.html %}
    {% endfor %}
    <br />
  {% endif %}
  
  {% comment %} Journal Publications for this year {% endcomment %}
  {% assign year_journal = year_group.items | where: "category", "journal" %}
  {% if year_journal.size > 0 %}
    <h3 class="publication-category-header">Journal Publications</h3>
    {% for post in year_journal %}
      {% include archive-single-publication.html %}
    {% endfor %}
    <br />
  {% endif %}
  
  {% comment %} Workshop Papers for this year {% endcomment %}
  {% assign year_workshop = year_group.items | where: "category", "workshop" %}
  {% if year_workshop.size > 0 %}
    <h3 class="publication-category-header">Workshop Papers</h3>
    {% for post in year_workshop %}
      {% include archive-single-publication.html %}
    {% endfor %}
    <br />
  {% endif %}
  
  {% comment %} Preprints for this year {% endcomment %}
  {% assign year_preprint = year_group.items | where: "category", "preprint" %}
  {% if year_preprint.size > 0 %}
    <h3 class="publication-category-header">Preprints</h3>
    {% for post in year_preprint %}
      {% include archive-single-publication.html %}
    {% endfor %}
    <br />
  {% endif %}
  
  <hr style="margin: 2em 0;" />
{% endfor %}
