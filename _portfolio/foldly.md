---
layout: default
title: Foldly
img: "assets/img/portfolio/foldly/app_icon.png"
gallery: "assets/img/portfolio/foldly/app/"
description: "A travel journal app with custom albums, photo organization using AI-powered image recognition, and social features. Built from scratch with 60fps scrolling performance."
---

# {{ page.title }}

<div style="display: flex; align-items: flex-start; gap: 32px; margin-bottom: 32px; flex-wrap: wrap;">
  <img src="{{ page.img | relative_url }}" alt="{{ page.title }} icon" style="width: 120px; height: 120px; object-fit: contain; border-radius: 24px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
  <div style="flex: 1; min-width: 300px;">
    <p style="font-size: 18px; line-height: 28px; margin: 0;">Foldly was a travel journal application that allowed users to create custom albums to organize photos. The app utilized AI-powered image recognition and tagging to assist with photo organization.</p>
    <div style="margin-top: 16px; display: flex; gap: 24px;">
      <div>
        <div style="font-size: 24px; font-weight: 500; color: var(--md-primary);">5K</div>
        <div style="font-size: 14px; color: rgba(0,0,0,0.6);">Daily Active Users</div>
      </div>
      <div>
        <div style="font-size: 24px; font-weight: 500; color: var(--md-primary);">60fps</div>
        <div style="font-size: 14px; color: rgba(0,0,0,0.6);">Smooth Scrolling</div>
      </div>
    </div>
  </div>
</div>

## Major Contributions

1. The main photo and video scroll feed:
	+ I worked on building the UI using ASDK, also known as Texture, by Pintrest and Facebook. This allowed the feed to run at 60 frames per second as most of the work was done on a background thread. This was implemented using a frame and internal stacklayout. This allowed a smooth user experience.
	+ I implemented the ability for the user to toggle to a grid viewing format when previewing photos and videos, as well as improving transition effects between various layouts.

2. Introduced the notes feature and search:
	+ I introduced the feature of adding notes to photos, allowing users to create notes to each photo similar to instagram except private notes.
	+ I introduced a search functionality that allowed a user to search for photos quickly and efficiently from notes and various other methods.

3. Coached the client through a successful launch into the marketplace:
	+ I worked with the client to gather requirements for a MVP and advised in releasing the app in various stages. 
	Successfully marketed the app and helped build an audience.
	+ The app captured an audience of 5k Daily active users then was promptly shutdown after the business model was not shown to profitable.

## App Screenshots

<style>
  .app-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 20px;
    margin: 32px 0;
  }
  
  .app-gallery img {
    width: 100%;
    height: auto;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    transition: all 0.3s;
    background: #f5f5f5;
  }
  
  .app-gallery img:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 24px rgba(0,0,0,0.15);
  }
</style>

<div class="app-gallery">
  <img src="/assets/img/portfolio/foldly/app/b.jpg" alt="Foldly screenshot">
  <img src="/assets/img/portfolio/foldly/app/c.jpg" alt="Foldly screenshot">
  <img src="/assets/img/portfolio/foldly/app/d.jpg" alt="Foldly screenshot">
  <img src="/assets/img/portfolio/foldly/app/e.png" alt="Foldly screenshot">
  <img src="/assets/img/portfolio/foldly/app/g.jpg" alt="Foldly screenshot">
</div>


