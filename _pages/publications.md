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

{% comment %} Get all publications by category {% endcomment %}
{% assign conference_pubs = site.publications | where: "category", "conference" | sort: "date" | reverse %}
{% assign journal_pubs = site.publications | where: "category", "journal" | sort: "date" | reverse %}
{% assign workshop_pubs = site.publications | where: "category", "workshop" | sort: "date" | reverse %}
{% assign preprint_pubs = site.publications | where: "category", "preprint" | sort: "date" | reverse %}

{% comment %} Group conference publications by year {% endcomment %}
{% assign conference_years = conference_pubs | group_by_exp: "pub", "pub.date | date: '%Y'" | sort: "name" | reverse %}

{% comment %} Table of Contents {% endcomment %}
<div class="publications-toc">
  <h2>Table of Contents</h2>
  <ul>
    <li><a href="#conference-publications">Conference Publications</a>
      <ul>
        {% for year_group in conference_years %}
          <li><a href="#year-{{ year_group.name }}">{{ year_group.name }}</a></li>
        {% endfor %}
      </ul>
    </li>
    <li><a href="#journal-publications">Journal Publications</a></li>
    <li><a href="#workshop-papers">Workshop Papers</a></li>
    <li><a href="#preprints">Preprints</a></li>
  </ul>
</div>

<hr style="margin: 2em 0;" />

{% comment %} Conference Publications (grouped by year) {% endcomment %}
<h2 id="conference-publications" class="publication-section-header">Conference Publications</h2>

{% for year_group in conference_years %}
  <h3 id="year-{{ year_group.name }}" class="publication-year-header">{{ year_group.name }}</h3>
  {% for post in year_group.items %}
    {% include archive-single-publication.html %}
  {% endfor %}
  <br />
{% endfor %}

<hr style="margin: 2em 0;" />

{% comment %} Journal Publications {% endcomment %}
<h2 id="journal-publications" class="publication-section-header">Journal Publications</h2>

{% for post in journal_pubs %}
  {% include archive-single-publication.html %}
{% endfor %}

<hr style="margin: 2em 0;" />

{% comment %} Workshop Papers {% endcomment %}
<h2 id="workshop-papers" class="publication-section-header">Workshop Papers</h2>

{% for post in workshop_pubs %}
  {% include archive-single-publication.html %}
{% endfor %}

<hr style="margin: 2em 0;" />

{% comment %} Preprints {% endcomment %}
<h2 id="preprints" class="publication-section-header">Preprints</h2>

{% for post in preprint_pubs %}
  {% include archive-single-publication.html %}
{% endfor %}
