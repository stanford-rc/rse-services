---
title:  "cvat"
date:   2020-09-01 2:00:21 -0500
image: cvat.png
github: https://github.com/stanford-rc/gcp-cvat-stanford
project_url: https://github.com/stanford-rc/gcp-cvat-stanford
categories: [web, django]
description: Deployment of cvat, a front-end and video database intended to allow for easy image annotation on Google Cloud.
status: completed
size: small
badges:
 - type: info
   tag: web
 - type: info
   tag: django
 - type: info
   tag: google-compute-engine
tags:
 - google-compute-engine
 - image-progressing
 - containers
 - web
 - django
---

### Goals
CVAT ([https://github.com/opencv/cvat](https://github.com/opencv/cvat)) is an interactive annotation interface to allow for manual annotation of images, and then further modeling. A lab at Stanford needed a cloud instance deployed for (shared) annotation of a few thousand images. Currently, the data are being annotated on local instances, and this makes communication and data consolidation challenging. The goals for this project included:

- Deployment of cvat on a Google Cloud Project instance
- networking
- ip address with https
- sufficient size for storage and images
- backup of instance and uploaded data

We discussed needs for the server, database, and backup, and then the interface was created, deployed, and documented, and handed off to the lab for testing. [Complete documentation](https://github.com/stanford-rc/gcp-cvat-stanford) was kept for reproduibility.

### Proposal

An instance on Compute Engine was deployed based on conversation between the lab contact and RSE. 
Ultimately GPUs were decided to not be used because of cost. The lab verified that video
content is already de-identified and there is no high risk data. The lab tested the interface
and was happy with the result. 


