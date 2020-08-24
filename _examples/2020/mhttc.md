---
title:  "MHTTC Network"
date:   2020-06-20 2:00:21 -0500
image: mhttc.png
github: https://github.com/vsoch/mhttc
project_url: https://vsoch.github.io/mhttc
categories: [web, django]
description: A group wanted a custom interweb for a local and set of national centers. The interface would allow invitation only access, and then generation of trainings, projects, and certificates.
status: completing
size: medium
badges:
 - type: info
   tag: web
 - type: info
   tag: django
 - type: info
   tag: google-app-engine
tags:
 - google-app-engine
 - containers
 - web
 - django
---

### Goals: 

The goals for the project were the following:

 - An open-source, version controlled code base (GitHub)
 - An interweb for centers to log in 
   - allowing center members to:
     - create and edit projects owned by their center
     - see projects owned by other centers (but not edit)
     - create certificate templates for training
     - upload participant lists that have permission to render the certificates
     - possibly include a simple profile page
   - allowing participants to:
     - be emailed with a link to retrieve certificates
     - enter an email and training session to download
 - Containerization to support local development
- Deployment to either Google App Engine or Google Compute (whichever costs less)


### Proposal

After a consultation, the RSE made the following recommendations:

 - Given sparse usage, Google App Engine with an external database would be the most cost effective
 - Develop open source project locally and deploy to Google App Engine regularly to get feedback
 - Weekly Updates

### Summary

The project is nearing completion. We learned that Google App Engine is a great
resources for quick deployment, and for small apps, is much more cost effective
than self-hosting on Google Cloud Compute Engine.
