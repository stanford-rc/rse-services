---
title:  "NE Cyberteam Portal"
date:   2019-09-02 2:00:21 -0500
image: cyberteam.png
github: https://www.github.com/hpsee/cyberteam
project_url: https://hpsee.github.io/cyberteam
categories: [portal, web]
description: This is a small documentation project that resulted in a finished web portal with content and requested views, along with a base project template for the community to enjoy.
status: completed
size: small
badges:
 - type: info
   tag: web
tags:
 - documentation
 - jekyll
 - github-pages
---

### Goals: 

To create a web interface to serve resources, projects, and people, including:

**Template:**
 - A base template that support projects, people, tags, and resources (done)
 - Styling of base template to match Cyberteam branding (done)
 - Completely statically hosted (no hosting costs or databases)

**People**
 - Researcher, Staff, and Student pages to describe contributors
 - Contributions and permissions via GitHub (version controlled)

**Resources**
 - A resources table with descriptions and links to external resources
Projects pages contributed by students

### Proposal

After discussion with the project requester, the RSE proposed to move forward with the following steps:

 - Develop a template with basic requirements for projects, and pages
 - The template should be styled to the current Cyberteam branding
 - The template should be customized to have project, resource, and people layouts to match the content needed by the Cyberteam site
 - The content itself needs to be migrated (likely a manual process)
 - Documentation should be written to support adding projects, people, news, resources (in progress)

### Completed

The RSE developed a base template, [sb-admin jekyll]({{ site.baseurl }}/docs/resources/documentation#sb-admin-jekyll),
that included charts, buttons, and an overall layout that would be suited for customization for the Cyberteam site.
The template was then instantiated at [https://www.github.com/hpsee/cyberteam](https://www.github.com/hpsee/cyberteam) 
and [further developed](https://hpsee.github.io/cyberteam) to include custom styling, projects and resources, tags, and search.
Hundreds of previous entries were migrated to the site.

![{{ site.baseurl }}/assets/img/examples/cyberteam-home.png]({{ site.baseurl }}/assets/img/examples/cyberteam-home.png)

The entire project was completed over a weekend, plus in the evenings of a few days the following week. This is considered
a relatively small documentation project, with the added feature of designing a new template that the community
can enjoy.
