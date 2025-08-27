---
layout: default
title: Foldly
feature-img: "assets/img/portfolio/foldly/title.png"
img: "assets/img/portfolio/foldly/app_icon.png"
gallery: "assets/img/portfolio/foldly/app/"
---

![image]({{ page.img | relative_url }})

Foldly was a project that required the development of a travel journal application from scratch. This app allowed users to create custom albums to organize photos. Foldly utilized tags and a embedded database that was using image content recognition to assist with organization.

Building the app from scratch, I built the following features:

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

{% include gallery.html gallery_path=page.gallery %}


