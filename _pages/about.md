---
layout: about
title: about
permalink: /
subtitle:

profile:
  align: right
  image: prof_pic.jpeg
  address: >
    <p>Gerberding Hall</p>
    <p>University of Washington</p>
    <p>1400 NE Campus Pkwy</p>
    <p> Seattle, WA 98195</p>
display_categories: [work]
news: true  # includes a list of news items
selected_papers: true # includes a list of papers marked as "selected={true}"
social: true  # includes social icons at the bottom of the page
---
I'm Joe Bak-Coleman, a computational social scientist and postdoctoral fellow at the [University of Washington Center for an Informed Public](https://www.cip.uw.edu/) and the [eScience Institute](https://escience.washington.edu/). I earned my PhD in [Ecology and Evolutionary](https://eeb.princeton.edu/) at Princeton University in 2020, working with [Iain Couzin](https://collectivebehaviour.com/people/couzin-iain/) and [Dan Rubenstein](https://eeb.princeton.edu/people/daniel-rubenstein).

My research is broadly focused on understanding how the actions and interactions of individuals give rise to patterns of collective behavior. I'm particularly interested in how collectives make decisions when faced with uncertainty. This is a common problem faced by nervous systems, animal groups, scientists, and human society alike. My research focuses on understanding commonalities across these systems and discerning what makes collectives work and how they go awry. Over the past decade, this has led my work from nervous systems and animal groups to a recent emphasis on understanding the consequences of social media at scale.

<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
