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
  
  <style>
    .client-logos {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 24px;
      margin: 40px 0;
      align-items: center;
      justify-items: center;
    }
    
    .client-logo {
      width: 120px;
      height: 80px;
      display: flex;
      align-items: center;
      justify-content: center;
      filter: grayscale(100%);
      opacity: 0.6;
      transition: all 0.3s;
    }
    
    .client-logo:hover {
      filter: grayscale(0%);
      opacity: 1;
      transform: scale(1.05);
    }
    
    .client-logo img {
      max-width: 100%;
      max-height: 100%;
      object-fit: contain;
    }
  </style>
  
  <div class="client-logos">
    <div class="client-logo">
      <svg viewBox="0 0 320 320" style="width: 50px; height: 50px;">
        <path d="M279.14 288l14.22-92.66h-88.91v-60.13c0-25.35 12.42-50.06 52.24-50.06h40.42V6.26S260.43 0 225.36 0c-73.22 0-121.08 44.38-121.08 124.72v70.62H22.89V288h81.39v224h100.17V288z" fill="#1877F2"/>
      </svg>
    </div>
    <div class="client-logo">
      <svg viewBox="0 0 814 1000" style="width: 50px; height: 50px;">
        <path d="M788.1 340.9c-5.8 4.5-108.2 62.2-108.2 190.5 0 148.4 130.3 200.9 134.2 202.2-.6 3.2-20.7 71.9-68.7 141.9-42.8 61.6-87.5 123.1-155.5 123.1s-85.5-39.5-164-39.5c-76.5 0-103.7 40.8-165.9 40.8s-105.6-57-155.5-127C46.7 790.7 0 663 0 541.8c0-194.4 126.4-297.5 250.8-297.5 66.1 0 121.2 43.4 162.7 43.4 39.5 0 101.1-46 176.3-46 28.5 0 130.9 2.6 198.3 99.2zm-234-181.5c31.1-36.9 53.1-88.1 53.1-139.3 0-7.1-.6-14.3-1.9-20.1-50.6 1.9-110.8 33.7-147.1 75.8-28.5 32.4-55.1 83.6-55.1 135.5 0 7.8 1.3 15.6 1.9 18.1 3.2.6 8.4 1.3 13.6 1.3 45.4 0 102.5-30.4 135.5-71.3z" fill="#000000"/>
      </svg>
    </div>
    <div class="client-logo">
      <svg viewBox="0 0 111 30" style="width: 90px; height: 30px;">
        <path d="M105.06 7.88c-1.34-1.61-3.57-2.4-6.65-2.4h-8.58v19.04h8.58c3.08 0 5.31-.8 6.65-2.4 1.35-1.61 2.03-4.16 2.03-7.62s-.68-6.01-2.03-7.62zM44.48 7.88c-1.35-1.61-3.57-2.4-6.66-2.4h-8.58v19.04h8.58c3.09 0 5.31-.8 6.66-2.4 1.34-1.61 2.02-4.16 2.02-7.62s-.68-6.01-2.02-7.62zM0 0v30h111V0H0zm25.78 22.22c-.71.95-1.67 1.67-2.88 2.16-1.21.49-2.63.73-4.27.73H8.89V4.9h9.74c1.64 0 3.06.25 4.27.73 1.21.49 2.17 1.21 2.88 2.16s1.04 2.13 1.04 3.53v7.37c0 1.4-.33 2.58-1.04 3.53zm25.02.55c-1.02 1.24-2.39 2.17-4.1 2.8-1.71.62-3.69.93-5.92.93h-13.7V3.5h13.7c2.23 0 4.21.31 5.92.93 1.71.63 3.08 1.56 4.1 2.8s1.52 2.79 1.52 4.65v7.75c0 1.86-.5 3.41-1.52 4.64zm25.13 1.74h-9.62L63.59 18h-8.25v6.51h-8.62V3.5h16.13c2.08 0 3.88.37 5.38 1.1 1.51.74 2.66 1.78 3.46 3.14.8 1.35 1.2 2.92 1.2 4.71 0 1.83-.42 3.42-1.27 4.78-.84 1.36-2.06 2.41-3.65 3.13l4.96 8.15zM89.4 24.51h-8.9V3.5h8.9v21.01zm21.68-2.29c-1.02 1.24-2.38 2.17-4.1 2.8-1.71.62-3.68.93-5.92.93H87.37V3.5h13.69c2.24 0 4.21.31 5.92.93 1.72.63 3.08 1.56 4.1 2.8 1.02 1.23 1.53 2.79 1.53 4.65v7.75c0 1.86-.51 3.41-1.53 4.64z" fill="#E50914"/>
      </svg>
    </div>
    <div class="client-logo">
      <img src="/assets/img/portfolio/clients/bellmedia.jpg" alt="Bell Media">
    </div>
    <div class="client-logo">
      <img src="/assets/img/portfolio/clients/td.png" alt="TD">
    </div>
    <div class="client-logo">
      <img src="/assets/img/portfolio/clients/thrive.png" alt="Thrive">
    </div>
    <div class="client-logo">
      <img src="/assets/img/portfolio/clients/kiwi.png" alt="Kiwi">
    </div>
    <div class="client-logo">
      <img src="/assets/img/portfolio/clients/papaceo.png" alt="Papa Ceo">
    </div>
    <div class="client-logo">
      <img src="/assets/img/portfolio/clients/chezdine.png" alt="Chez Dine">
    </div>
  </div>
  
  <p style="color: rgba(0,0,0,0.6); margin-bottom: 24px;">
    For client confidentiality reasons, detailed case studies are available upon request.
  </p>
  <a href="mailto:michael.chung@databites.ca" class="btn btn-primary">DISCUSS YOUR PROJECT</a>
</div>