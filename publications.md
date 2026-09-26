---
layout: default
title: "Publications"
description: "Selected publications by Dr. Karuna Anna Sajeevan and collaborators."
---

<div class="page">
  <div class="container">
    <header class="page-header">
      <div class="eyebrow">Publications</div>
      <h1>Research contributions</h1>
      <p>
        Selected publications spanning computational chemistry, molecular
        simulation, AI/ML, protein engineering, peptides, healthcare and
        sustainable molecular science.
      </p>
    </header>

    <div class="pub-filter" id="pub-filter">
      <button class="active" data-filter="all">All</button>
      {% assign categories = site.data.publications | map: "categories" | join: "|" | split: "|" | uniq | sort %}
      {% for category in categories %}
        <button data-filter="{{ category | slugify }}">{{ category }}</button>
      {% endfor %}
    </div>

    {% assign pubs = site.data.publications | sort: "year" | reverse %}
    {% assign current_year = "" %}

    {% for pub in pubs %}
      {% if pub.year != current_year %}
        {% assign current_year = pub.year %}
        <h2 class="pub-year">{{ current_year }}</h2>
      {% endif %}

      <article class="publication"
               data-categories="{% for category in pub.categories %}{{ category | slugify }} {% endfor %}">
        <h3>
          {% if pub.url %}
            <a href="{{ pub.url }}" target="_blank" rel="noopener">{{ pub.title }}</a>
          {% else %}
            {{ pub.title }}
          {% endif %}
        </h3>
        <div class="authors">{{ pub.authors }}</div>
        <div class="journal">
          <em>{{ pub.journal }}</em>
          {% if pub.doi %} · DOI: {{ pub.doi }}{% endif %}
        </div>
        <div class="tags">
          {% for category in pub.categories %}
            <span class="tag">{{ category }}</span>
          {% endfor %}
        </div>
      </article>
    {% endfor %}

    <div class="callout">
      The publication list is maintained as a curated lab record. For the
      identifier-based publication record, see
      <a href="https://orcid.org/0000-0002-9093-3845" target="_blank" rel="noopener">ORCID</a>.
    </div>
  </div>
</div>

<script>
  const filterButtons = document.querySelectorAll('#pub-filter button');
  const publications = document.querySelectorAll('.publication');

  filterButtons.forEach(button => {
    button.addEventListener('click', () => {
      filterButtons.forEach(b => b.classList.remove('active'));
      button.classList.add('active');

      const filter = button.dataset.filter;
      publications.forEach(pub => {
        const cats = pub.dataset.categories.split(' ');
        pub.style.display = (filter === 'all' || cats.includes(filter)) ? '' : 'none';
      });
    });
  });
</script>
