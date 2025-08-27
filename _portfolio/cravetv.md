---
layout: default
title: CraveTV 2
img: "assets/img/portfolio/crave/app_icon.png"
gallery: "assets/img/portfolio/crave/app/"
project_date: March 2018 - March 2019
description: "Bell Media's streaming app with 400K daily active users and 3M+ downloads. Led development of offline downloads, accessibility features, and cross-platform support."
---

# {{ page.title }}

<div style="display: flex; align-items: flex-start; gap: 32px; margin-bottom: 32px; flex-wrap: wrap;">
  <img src="{{ page.img | relative_url }}" alt="{{ page.title }} icon" style="width: 120px; height: 120px; object-fit: contain; border-radius: 24px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
  <div style="flex: 1; min-width: 300px;">
    <div style="font-size: 18px; color: rgba(0,0,0,0.6); margin-bottom: 8px;">{{ page.project_date }}</div>
    <p style="font-size: 18px; line-height: 28px; margin: 0;">At Bell Media, I worked on the popular CraveTV 2 mobile application. This app required extensive cross communication and work across the organization.</p>
    <div style="margin-top: 16px; display: flex; gap: 24px;">
      <div>
        <div style="font-size: 24px; font-weight: 500; color: var(--md-primary);">400K</div>
        <div style="font-size: 14px; color: rgba(0,0,0,0.6);">Daily Active Users</div>
      </div>
      <div>
        <div style="font-size: 24px; font-weight: 500; color: var(--md-primary);">3M+</div>
        <div style="font-size: 14px; color: rgba(0,0,0,0.6);">Downloads</div>
      </div>
    </div>
  </div>
</div>

## Major Contributions

1. Accessibility Feature
	+ I introduced accessibility labels throughout the whole app for buttons and spec-ed out screens to allow a user with visual limitations to navigate the app more fluidly throughout the app. 

2. The Downloads Feature
	+ I gathered and implemented requirements necessary to introduce the ability to watch video's offline. The application had no ability to watch video's offline. I gathered requirements and cross coordinated with different teams to integrate and build the UI/UX and business logic behind the feature to enable this feature to allow videos to be downloaded and watched while the device was not connected to the internet.

3. The Analytics Integration
	+ Analytics helped the product team glean data to determine which features were successful and unsuccessful after every launch. My integration allowed the product team to measure the effectiveness of a UI/UX design and gave product insight into various features such as downloads and home screen. 

4. The iPad, tvOS Sections 
	+ The application required many of the screens to be functionally available for the iPad and tvOS, this required reworking of the UI, which was work done by the team and myself.

## App Screenshots

<style>
  .app-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
    margin: 24px 0;
  }
  
  .app-gallery img {
    width: 100%;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    transition: transform 0.3s;
  }
  
  .app-gallery img:hover {
    transform: scale(1.05);
    box-shadow: 0 4px 16px rgba(0,0,0,0.2);
  }
</style>

<div class="app-gallery">
  {% assign image_files = site.static_files | where: "path", page.gallery %}
  {% for image in image_files limit:6 %}
    <img src="{{ image.path | relative_url }}" alt="CraveTV screenshot">
  {% endfor %}
</div>


