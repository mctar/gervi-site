---
layout: page
title: Gallery
permalink: /gallery/
description: Visual notes from Gervi Labs projects.
---

<section class="gallery-filters">
  <div>
    <label for="gallery-project-filter">Project</label>
    <select id="gallery-project-filter" data-default="{{ page.project | default: 'all' }}">
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

<div class="gallery-lightbox" id="gallery-lightbox">
  <button class="lightbox-close" type="button" aria-label="Close gallery view">Close</button>
  <figure>
    <img src="" alt="">
    <figcaption></figcaption>
  </figure>
</div>

<script>
  (function () {
    var projectSelect = document.getElementById('gallery-project-filter');
    var yearSelect = document.getElementById('gallery-year-filter');
    var items = document.querySelectorAll('.gallery-item');
    var lightbox = document.getElementById('gallery-lightbox');
    var lightboxImg = lightbox.querySelector('img');
    var lightboxCaption = lightbox.querySelector('figcaption');
    var closeBtn = lightbox.querySelector('.lightbox-close');

    function filterGallery() {
      var project = projectSelect.value || projectSelect.dataset.default || 'all';
      var year = yearSelect.value;

      items.forEach(function (item) {
        var matchesProject = project === 'all' || item.dataset.project === project;
        var matchesYear = year === 'all' || item.dataset.year === year;
        item.style.display = (matchesProject && matchesYear) ? '' : 'none';
      });
    }

    projectSelect.addEventListener('change', filterGallery);
    yearSelect.addEventListener('change', filterGallery);

    function openLightbox(item) {
      var img = item.querySelector('img');
      var caption = item.querySelector('figcaption');
      lightboxImg.src = img.src;
      lightboxImg.alt = img.alt;
      lightboxCaption.textContent = caption ? caption.textContent : '';
      lightbox.classList.add('gallery-lightbox--open');
    }

    function closeLightbox() {
      lightbox.classList.remove('gallery-lightbox--open');
      lightboxImg.src = '';
      lightboxImg.alt = '';
      lightboxCaption.textContent = '';
    }

    items.forEach(function (item) {
      var img = item.querySelector('img');
      img.addEventListener('click', function () {
        openLightbox(item);
      });
    });

    closeBtn.addEventListener('click', closeLightbox);
    lightbox.addEventListener('click', function (event) {
      if (event.target === lightbox) {
        closeLightbox();
      }
    });
    document.addEventListener('keyup', function (event) {
      if (event.key === 'Escape' && lightbox.classList.contains('gallery-lightbox--open')) {
        closeLightbox();
      }
    });
  })();
</script>
