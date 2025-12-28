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

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

<a href="https://arxiv.org/abs/2407.04172v1" style="text-decoration: none; color: #99FF9FF;"> ChartGemma: Visual Instruction-tuning for Chart Reasoning in the Wild</a>  
**Ahmed Masry\***, Megh Thakkar\*, Aayush Bajaj, Aaryaman Kartha, Enamul Hoque, Shafiq Joty  
Published at **COLING 2025**
