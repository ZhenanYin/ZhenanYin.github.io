---
layout: page
title: Projects
permalink: /projects/
description: A growing collection of the cool projects.
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

<div class="projects-timeline">
{% assign sorted_projects = site.projects | sort: "year" | reverse %}
{% for project in sorted_projects %}
  <div class="project-item">
    <div class="project-row">
      {% if project.img %}
      <div class="project-image">
        <img src="{{ project.img | relative_url }}" alt="{{ project.title }}">
      </div>
      {% endif %}
      <div class="project-content">
        <h3 class="project-title">
          {% if project.redirect %}
            <a href="{{ project.redirect }}" target="_blank">{{ project.title }}</a>
          {% else %}
            <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
          {% endif %}
        </h3>
        
        {% if project.authors %}
          <p class="project-authors">{{ project.authors }}</p>
        {% endif %}
        
        <p class="project-description">{{ project.description }}</p>
        
        {% if project.venue %}
          <p class="project-venue"><em>{{ project.venue }}</em></p>
        {% endif %}
        
        {% if project.links %}
          <div class="project-links">
            {% for link in project.links %}
              <a href="{{ link.url }}" target="_blank" class="btn btn-sm z-depth-0" role="button">{{ link.name }}</a>
            {% endfor %}
          </div>
        {% endif %}
      </div>
    </div>
  </div>
{% endfor %}
</div>

<style>
.projects-timeline {
  max-width: 1000px;
  margin: 0 auto;
}

.project-item {
  margin-bottom: 3rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid #e0e0e0;
}

.project-item:last-child {
  border-bottom: none;
}

.project-row {
  display: flex;
  gap: 2rem;
  align-items: flex-start;
}

.project-image {
  flex-shrink: 0;
  width: 300px;
}

.project-image img {
  width: 100%;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.project-content {
  flex: 1;
}

.project-title {
  margin-top: 0;
  margin-bottom: 0.5rem;
  font-size: 1.5rem;
}

.project-title a {
  color: var(--global-theme-color);
  text-decoration: none;
}

.project-title a:hover {
  text-decoration: underline;
}

.project-authors {
  color: #666;
  font-size: 0.95rem;
  margin-bottom: 0.5rem;
}

.project-description {
  margin-bottom: 0.5rem;
}

.project-venue {
  color: #666;
  margin-bottom: 1rem;
}

.project-links {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.project-links .btn {
  background-color: var(--global-theme-color);
  color: white;
  border: none;
  padding: 0.4rem 1rem;
  text-decoration: none;
  border-radius: 4px;
  font-size: 0.9rem;
}

.project-links .btn:hover {
  opacity: 0.9;
}

@media (max-width: 768px) {
  .project-row {
    flex-direction: column;
  }
  
  .project-image {
    width: 100%;
  }
}
</style>