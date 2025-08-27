--- 
layout: default
title: Portfolio
permalink: /portfolio/
---

# Portfolio

<p style="font-size: 20px; line-height: 28px; color: rgba(0,0,0,0.6); margin-bottom: 32px;">iOS Apps and Projects I've Worked On</p>

<style>
  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 20px;
    margin-bottom: 48px;
  }
  
  .portfolio-card {
    background: var(--md-surface);
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    transition: all 0.3s;
    cursor: pointer;
    text-decoration: none;
    color: inherit;
    display: block;
  }
  
  .portfolio-card:hover {
    box-shadow: 0 8px 16px rgba(0,0,0,0.15);
    transform: translateY(-4px);
  }
  
  .portfolio-image {
    width: 100%;
    height: 180px;
    background: #f8f9fa;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    position: relative;
  }
  
  .portfolio-image img {
    width: 100px;
    height: 100px;
    object-fit: contain;
    border-radius: 20px;
  }
  
  .portfolio-content {
    padding: 20px;
  }
  
  .portfolio-title {
    font-size: 20px;
    font-weight: 500;
    margin: 0 0 8px 0;
    color: var(--md-text-color);
  }
  
  .portfolio-date {
    font-size: 14px;
    color: rgba(0,0,0,0.54);
    margin-bottom: 16px;
  }
  
  .portfolio-description {
    color: rgba(0,0,0,0.7);
    line-height: 1.6;
    margin: 0;
  }
  
  .portfolio-arrow {
    color: var(--md-primary);
    font-size: 14px;
    font-weight: 500;
    margin-top: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
</style>

## Featured iOS Apps

<div class="portfolio-grid">
  {% for project in site.portfolio %}
    <a href="{{ project.url | relative_url }}" class="portfolio-card">
      <div class="portfolio-image">
        {% if project.img %}
          <img src="{{ project.img | relative_url }}" alt="{{ project.title }} icon">
        {% else %}
          <span class="material-icons" style="font-size: 64px; color: rgba(0,0,0,0.2);">smartphone</span>
        {% endif %}
      </div>
      <div class="portfolio-content">
        <h3 class="portfolio-title">{{ project.title }}</h3>
        {% if project.project_date %}
          <div class="portfolio-date">{{ project.project_date }}</div>
        {% elsif project.date %}
          <div class="portfolio-date">{{ project.date | date: "%B %Y" }}</div>
        {% endif %}
        <p class="portfolio-description">
          {% if project.description %}
            {{ project.description }}
          {% else %}
            {{ project.content | strip_html | truncatewords: 25 }}
          {% endif %}
        </p>
        <div class="portfolio-arrow">
          View Details
          <span class="material-icons" style="font-size: 18px;">arrow_forward</span>
        </div>
      </div>
    </a>
  {% endfor %}
</div>

## Current and Past Clients

<div class="card" style="text-align: center; padding: 48px 24px;">
  <span class="material-icons" style="font-size: 48px; color: var(--md-primary); margin-bottom: 16px;">business_center</span>
  <h3 style="margin-bottom: 16px;">Enterprise Experience</h3>
  <p style="font-size: 18px; color: rgba(0,0,0,0.7); max-width: 600px; margin: 0 auto 24px;">
    I've had the privilege of working with amazing companies and startups, from media giants to innovative tech companies.
  </p>
  <p style="color: rgba(0,0,0,0.6); margin-bottom: 24px;">
    For client confidentiality reasons, detailed case studies are available upon request.
  </p>
  <a href="mailto:michael.chung@databites.ca" class="btn btn-primary">DISCUSS YOUR PROJECT</a>
</div>