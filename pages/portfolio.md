--- 
layout: default
title: Portfolio
permalink: /portfolio/
---

# Portfolio

<p style="font-size: 20px; line-height: 28px; color: rgba(0,0,0,0.6); margin-bottom: 32px;">iOS Apps and Projects I've Worked On</p>

## Featured Projects

<div style="display: grid; gap: 24px; margin-bottom: 48px;">
  {% for project in site.portfolio %}
    <div class="card" style="padding: 24px;">
      <h3>{{ project.title }}</h3>
      <p style="color: rgba(0,0,0,0.7); margin: 16px 0;">{{ project.excerpt | strip_html }}</p>
      <a href="{{ project.url | relative_url }}" class="btn btn-primary">VIEW DETAILS</a>
    </div>
  {% endfor %}
</div>

## Current and Past Clients

<div style="text-align: center; margin: 48px 0;">
  <p style="font-size: 18px; color: rgba(0,0,0,0.7);">I've had the privilege of working with amazing companies and startups.</p>
  <p style="margin-top: 24px;">For client confidentiality reasons, detailed case studies are available upon request.</p>
  <a href="mailto:michael.chung@databites.ca" class="btn btn-primary" style="margin-top: 16px;">GET IN TOUCH</a>
</div>