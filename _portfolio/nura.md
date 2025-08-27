---
layout: default
title: Nura
img: "assets/img/portfolio/nura/app_icon.png"
gallery: "assets/img/portfolio/nura/app/"
description: "Medical app that measures vitals using iPhone camera. First of its kind technology combining AI/ML with iOS to read heart rate, blood pressure, and stress levels."
---

# {{ page.title }}

<div style="display: flex; align-items: flex-start; gap: 32px; margin-bottom: 32px; flex-wrap: wrap;">
  <img src="{{ page.img | relative_url }}" alt="{{ page.title }} icon" style="width: 120px; height: 120px; object-fit: contain; border-radius: 24px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
  <div style="flex: 1; min-width: 300px;">
    <p style="font-size: 18px; line-height: 28px; margin: 0;">At Nuralogix, I developed a groundbreaking medical app that measures vitals using only the iPhone camera. This first-of-its-kind technology combines AI/ML with iOS to accurately read heart rate, blood pressure, and stress levels.</p>
    <div style="margin-top: 16px; display: flex; gap: 24px;">
      <div>
        <div style="font-size: 24px; font-weight: 500; color: var(--md-primary);">3</div>
        <div style="font-size: 14px; color: rgba(0,0,0,0.6);">Vital Signs Measured</div>
      </div>
      <div>
        <div style="font-size: 24px; font-weight: 500; color: var(--md-primary);">First</div>
        <div style="font-size: 14px; color: rgba(0,0,0,0.6);">Camera-based Medical App</div>
      </div>
    </div>
  </div>
</div>

## Major Contributions

1. Reading the Heart Rate, Blood Pressure, and Stress
	+ I worked alongside the Machine Learning team to build a service that allowed us to consume data from the iOS device. The device sent statistical data from video feed of the camera to the server using a websocket to allow the inference of the 3 vitals above. 
	+ I implemented the client side feature extraction process on the device side to allow inference to work efficiently on the server. 
	+ I built and designed the main page where the vitals were displayed to the user.

2. Application Design Documentation, Agile Process, and CI/CD
	+ I gathered and implemented requirements necessary to help with the development of the hardware device. I documented various image feature extraction pipelines and functions required to be ported over into C++ and built into libraries.
	+ I guided and implemented an agile process that was adopted by other members of the software team applications team.
	+ I integrated fastlane and jenkins to create a build process to allow the application to be delivered to stakeholders.

3. Designed and implemented the UI and trained DLib model to track a face model and features of the face
	+ I worked with an outside art team to implement the onboarding screens for Nura, and implemented the screens using Lotte
	+ I trained and implemented the mobile DLib model to capture fiducial points on the face and draw regions of interests.

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
  <img src="/assets/img/portfolio/nura/app/a.png" alt="Nura screenshot">
  <img src="/assets/img/portfolio/nura/app/b.png" alt="Nura screenshot">
  <img src="/assets/img/portfolio/nura/app/e.png" alt="Nura screenshot">
  <img src="/assets/img/portfolio/nura/app/f.png" alt="Nura screenshot">
  <img src="/assets/img/portfolio/nura/app/g.png" alt="Nura screenshot">
  <img src="/assets/img/portfolio/nura/app/h.png" alt="Nura screenshot">
</div>

