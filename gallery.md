---
layout: page
title: Gallery
permalink: /gallery/
description: Visual notes from Gervi Labs projects.
---

<section class="gallery-filters">
  <div>
    <label for="gallery-project-filter">Project</label>
    <select id="gallery-project-filter">
      <option value="all">All projects</option>
      {% assign project_titles = "" | split: "" %}
      {% for entry in site.data.gallery %}
        {% assign label = entry.project_title | default: entry.project %}
        {% unless project_titles contains label %}
          {% assign project_titles = project_titles | push: label %}
        {% endunless %}
      {% endfor %}
      {% assign project_titles = project_titles | sort %}
      {% for label in project_titles %}
        {% assign slug = "" %}
        {% for entry in site.data.gallery %}
          {% if entry.project_title == label %}
            {% assign slug = entry.project %}
            {% break %}
          {% endif %}
        {% endfor %}
        <option value="{{ slug | default: label | slugify }}">{{ label }}</option>
      {% endfor %}
    </select>
  </div>
  <div>
    <label for="gallery-year-filter">Year</label>
    <select id="gallery-year-filter">
      <option value="all">All years</option>
      {% assign years = site.data.gallery | map: "year" | uniq | sort %}
      {% for year in years %}
        <option value="{{ year }}">{{ year }}</option>
      {% endfor %}
    </select>
  </div>
</section>

<div class="gallery-grid" id="gallery-grid">
  {% for entry in site.data.gallery %}
    <figure class="gallery-item"
            data-project="{{ entry.project | default: entry.project_title | slugify }}"
            data-year="{{ entry.year }}">
      <img src="{{ entry.image | relative_url }}" alt="{{ entry.alt }}">
      {% if entry.caption %}
        <figcaption>{{ entry.caption }}</figcaption>
      {% endif %}
    </figure>
  {% endfor %}
</div>

<script>
  (function () {
    var projectSelect = document.getElementById('gallery-project-filter');
    var yearSelect = document.getElementById('gallery-year-filter');
    var items = document.querySelectorAll('.gallery-item');

    function filterGallery() {
      var project = projectSelect.value;
      var year = yearSelect.value;

      items.forEach(function (item) {
        var matchesProject = project === 'all' || item.dataset.project === project;
        var matchesYear = year === 'all' || item.dataset.year === year;
        item.style.display = (matchesProject && matchesYear) ? '' : 'none';
      });
    }

    projectSelect.addEventListener('change', filterGallery);
    yearSelect.addEventListener('change', filterGallery);
  })();
</script>
