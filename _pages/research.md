---
layout: archive
title: "Selected Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

<div class="category-filters" style="margin-bottom: 2em; text-align: center;">
  <button class="category-btn active" data-category="all">All</button>
  <button class="category-btn" data-category="academic">Academic</button>
  <button class="category-btn" data-category="policy">Policy</button>
  <button class="category-btn" data-category="other">Other</button>
</div>

<div class="research-category" data-category="academic">
<h2>Academic</h2>

{% for post in site.research reversed %}
	{% if post.category == 'academic' and post.visibility != 'hidden' %}
  		{% include archive-single.html %}
	{% endif %}
{% endfor %}
</div>

<div class="research-category" data-category="policy">
<h2>Policy</h2>

{% for post in site.research reversed %}
	{% if post.category == 'policy' and post.visibility != 'hidden' %}
  		{% include archive-single.html %}
	{% endif %}
{% endfor %}
</div>

<div class="research-category" data-category="other">
<h2>Other</h2>

{% for post in site.research reversed %}
	{% if post.category == 'other' and post.visibility != 'hidden' %}
  		{% include archive-single.html %}
	{% endif %}
{% endfor %}
</div>

<style>
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
}

.category-btn:hover {
  background-color: #f0f0f0;
}

.category-btn.active {
  background-color: #4a90e2;
  color: white;
  border-color: #4a90e2;
}

.research-category {
  display: none;
}

.research-category.active {
  display: block;
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const buttons = document.querySelectorAll('.category-btn');
  const categories = document.querySelectorAll('.research-category');

  // Show all categories by default
  categories.forEach(cat => cat.classList.add('active'));

  buttons.forEach(button => {
    button.addEventListener('click', function() {
      const selectedCategory = this.getAttribute('data-category');

      // Update button states
      buttons.forEach(btn => btn.classList.remove('active'));
      this.classList.add('active');

      // Update category visibility
      categories.forEach(cat => {
        if (selectedCategory === 'all') {
          cat.classList.add('active');
        } else if (cat.getAttribute('data-category') === selectedCategory) {
          cat.classList.add('active');
        } else {
          cat.classList.remove('active');
        }
      });
    });
  });
});
</script>