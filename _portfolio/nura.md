---
layout: post
title: Nura
feature-img: "assets/img/portfolio/nura/title_hor.png"
img: "assets/img/portfolio/nura/app_icon.png"
gallery: "assets/img/portfolio/nura/app/"
---

At Nuralogix, I worked as part of a development team on the medical app Nura. It had a unique application and was the first of its kind, where it was able to glean vitals using the standard camera on your iPhone. This app required extensive cross collaboration between AI Scientists and stakeholders. My role was to gather requirements and ensure that usability was at the core of this project, as well as to develop the integration between Machine Learning and iOS devices.. I was also designated to coach the team through the process of building and delivery, as this was their first app. 

Building the app from scratch, I contributed the following:

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

{% include gallery.html gallery_path=page.gallery %}

