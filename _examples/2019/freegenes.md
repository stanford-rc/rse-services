---
title:  "FreeGenes"
date:   2019-09-02 2:00:21 -0500
image: freegenes.png
github: https://www.github.com/vsoch/freegenes
project_url: https://vsoch.github.io/freegenes
categories: [web, api]
description: This is a larger project to implement order and lab management services for open source genomics. The project includes development of front-end and back-end views, an API, efficient query, containers, documentation, and cloud deployment.
status: completed
size: large
badges:
 - type: info
   tag: web
 - type: info
   tag: containers
tags:
 - documentation
 - containers
 - django
 - api
---

### Goals: 

To create a web interface and API to serve freegenes, including:

 - Front and back end views, along with the current API
 - Front end template / design for the site (simple, using current colors of freegenes)
 - Different levels of administrator access, along with user access to create orders
 - Front end views for users (to create orders) and administrators (to manage them)
 - Authentication options should be selected by the deployer, OAuth 2 to start

### Proposal

After a consultation, the RSE made the following recommendations:

 - To maximize contributions from the lab, Python would be used for the backend, specifically Django.
 - A specific cloud provider should be used to maximize already existing relationships.
 - Measures would be taken to not store any user information on the server beyond a username and email for OAuth2
 - The project would be developed with a long term goal of generalization in mind - any lab could deploy an instance.

And the work proposal generally came down to designing the database models, front end views, back end views, API and user permissions, along with complete documentation. 

### In Progress

The bulk of the stated work was completed in under a month, and the RSE additionally developed a Python client to interact with the API. A development (testing) server is expected to be deployed shortly, and this will be followed by additional requests from the lab for changes and features.

This is considered a larger project, as it includes front-end, back-end, API development, container orchestration, cloud deployment, client development, and documentation.
