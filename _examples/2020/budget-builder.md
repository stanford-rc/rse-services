---
title:  "Budget Builder"
date:   2020-03-02 2:00:21 -0500
image: budget-builder.png
github: https://github.com/vsoch/drupal-docker-compose
project_url: https://researchbudget.stanford.edu
categories: [web, drupal]
description: A legacy Drupal installation needed several features and views added. This project first reproduced the production environment with docker-compose, and then did the development changes, and when they were tested and working, the changes were done on the production server.
status: completed
size: medium
badges:
 - type: info
   tag: web
 - type: info
   tag: drupal
tags:
 - drupal
 - containers
 - web
---

### Goals: 

To update a legacy Drupal installation with several new features. The description here is vague intentionally. The work included:

 - Creating a container based development environment to reproduce the production server
 - Addition of a new user group that should be given access to see a particular kind of study.
 - Notifications for study submission

### Proposal

After a consultation, the RSE made the following recommendations:

 - Develop a dockerized environment to reproduce the production server
 - Develop changes locally, write up instructions, review with requester
 - Deploy changes to production server


### Summary

The project was successfully completed. While the work for the actual server cannot
be shared, one of the outputs, the [Dockerized drupal](https://github.com/vsoch/drupal-docker-compose)
repository is a resource that might be useful to others.
