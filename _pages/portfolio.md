---
layout: archive
title: "Selected Works"
permalink: /portfolio/
author_profile: true
---

{% include base_path %}

<div class="portfolio-filter-container">
  <input type="radio" name="category" id="filter-all" value="all" checked>
  <input type="radio" name="category" id="filter-academic" value="academic">
  <input type="radio" name="category" id="filter-policy" value="policy">
  <input type="radio" name="category" id="filter-other" value="other">

  <div class="category-filters">
    <label for="filter-all" class="category-btn active">All</label>
    <label for="filter-academic" class="category-btn">Academic</label>
    <label for="filter-policy" class="category-btn">Policy</label>
    <label for="filter-other" class="category-btn">Other</label>
  </div>

  <div class="research-category" data-category="all">
    <h2>All</h2>
    {% for post in site.portfolio reversed %}
      {% if post.visibility != 'hidden' %}
        {% include archive-single.html %}
      {% endif %}
    {% endfor %}
  </div>

  <div class="research-category" data-category="academic">
    <h2>Academic</h2>
    {% for post in site.portfolio reversed %}
      {% if post.category == 'academic' and post.visibility != 'hidden' %}
        {% include archive-single.html %}
      {% endif %}
    {% endfor %}
  </div>

  <div class="research-category" data-category="policy">
    <h2>Policy</h2>
    {% for post in site.portfolio reversed %}
      {% if post.category == 'policy' and post.visibility != 'hidden' %}
        {% include archive-single.html %}
      {% endif %}
    {% endfor %}
  </div>

  <div class="research-category" data-category="other">
    <h2>Long-form Media Appearances</h2>

    {% for post in site.appearances reversed %}
      {% if post.visibility != 'hidden' %}
        {% include archive-single.html %}
      {% endif %}
    {% endfor %}

    <h2>Other</h2>
    {% for post in site.portfolio reversed %}
      {% if post.category == 'other' and post.visibility != 'hidden' %}
        {% include archive-single.html %}
      {% endif %}
    {% endfor %}
  </div>
</div>

<style>
/* Hide radio inputs */
input[type="radio"][name="category"] {
  display: none;
}

.category-filters {
  margin-bottom: 2em;
  text-align: center;
}

.category-btn {
  padding: 10px 20px;
  margin: 0 10px;
  border: 2px solid #999;
  background-color: white;
  color: #333;
  border-radius: 4px;
  cursor: pointer;
  font-size: 14px;
  transition: all 0.3s ease;
  display: inline-block;
}

.category-btn:hover {
  background-color: #f0f0f0;
}

/* Style the label for the checked radio */
#filter-all:checked ~ .category-filters label[for="filter-all"],
#filter-academic:checked ~ .category-filters label[for="filter-academic"],
#filter-policy:checked ~ .category-filters label[for="filter-policy"],
#filter-other:checked ~ .category-filters label[for="filter-other"] {
  background-color: #4a90e2;
  color: white;
  border-color: #4a90e2;
}

.research-category {
  display: none;
}

/* Show the appropriate category based on which radio is checked */
#filter-all:checked ~ [data-category="all"],
#filter-academic:checked ~ [data-category="academic"],
#filter-policy:checked ~ [data-category="policy"],
#filter-other:checked ~ [data-category="other"] {
  display: block;
}
</style>

