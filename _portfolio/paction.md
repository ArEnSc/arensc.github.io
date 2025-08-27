---
layout: default
title: ParticipACTION
img: "assets/img/portfolio/paction/app_icon.png"
gallery: "assets/img/portfolio/paction/app/"
description: "Canada's famous fitness app with 100K+ users. Built gamification features including badges, rewards system, and social profiles to encourage healthy living."
---

# {{ page.title }}

<div style="display: flex; align-items: flex-start; gap: 32px; margin-bottom: 32px; flex-wrap: wrap;">
  <img src="{{ page.img | relative_url }}" alt="{{ page.title }} icon" style="width: 120px; height: 120px; object-fit: contain; border-radius: 24px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
  <div style="flex: 1; min-width: 300px;">
    <p style="font-size: 18px; line-height: 28px; margin: 0;">I worked on Canada's famous fitness application, ParticipACTION. The app encourages healthy living through gamification, social features, and rewards.</p>
    <div style="margin-top: 16px; display: flex; gap: 24px;">
      <div>
        <div style="font-size: 24px; font-weight: 500; color: var(--md-primary);">100K+</div>
        <div style="font-size: 14px; color: rgba(0,0,0,0.6);">Active Users</div>
      </div>
      <div>
        <div style="font-size: 24px; font-weight: 500; color: var(--md-primary);">National</div>
        <div style="font-size: 14px; color: rgba(0,0,0,0.6);">Canadian Health Initiative</div>
      </div>
    </div>
  </div>
</div>

## Major Contributions

1. Badges List, Details and Modals, and CMS
	+ I introduced the awards system to the application. Where users are given awards based off of the goals they achieve.
	+ I introduced modals that showed when an award was achieved to signal to the user that they had achieved them
	+ I also built detail views to allow the user to understand the badges they had won.
	+ This included work to add an CMS into the application, load articles and pages and content using Prismic.

2. Rewards List
	+ I gathered and implemented requirements, for the rewards system and integrated the system to provide weekly draws, and display to users if they had won prizes.

3. The Analytics Integration
	+ Analytics helped the product manager glean data to determine which features were successful and unsuccessful after every launch. My integration allowed the the product manager to measure the effectiveness of the application and gave product insight into various features.  

4. Profile and Edit Profile
	+ I built the profile section of the application allowing a user to create their profile and edit and modify the profile.
	+ This also included integration with Facebook signin.
 
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
  <img src="/assets/img/portfolio/paction/app/a.PNG" alt="ParticipACTION screenshot">
  <img src="/assets/img/portfolio/paction/app/b.PNG" alt="ParticipACTION screenshot">
  <img src="/assets/img/portfolio/paction/app/c.PNG" alt="ParticipACTION screenshot">
  <img src="/assets/img/portfolio/paction/app/d.PNG" alt="ParticipACTION screenshot">
  <img src="/assets/img/portfolio/paction/app/e.PNG" alt="ParticipACTION screenshot">
  <img src="/assets/img/portfolio/paction/app/f.PNG" alt="ParticipACTION screenshot">
</div>

