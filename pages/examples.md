---
layout: page
title: Example Projects
permalink: /examples
disable_editable: yes
---

# Example Projects

The following projects are a sample of those that are in progress or completed by RSE Services.
Each of these projects has a full support plan with a statement of work, and only the overall
goals and links to project content are shared here.

{% for project in site.examples %}
<h2 id="{{ project.title | slugify }}">{{ project.title }}</h2>
{% if project.image %}<a href="{{ site.baseurl }}{{ project.url }}"><img style="width:50%; float:right; margin-left:30px; margin-top:40px" src="{{ site.baseurl }}/assets/img/examples/{{ project.image }}"></a>{% endif %}
{% include projects/status.html status=project.status %}<span class="badge badge-secondary">size {{ project.size }}</span>

{{ project.description }}

<a href="{{ site.baseurl }}{{ project.url }}"><button class="btn btn-primary">View</button></a>

<hr>

{% endfor %}

<br><br>

If you like what you see and want some help for your own projects, please open a <a href="{{ site.baseurl }}/request/"><button class="btn btn-success btn-lg" >New Request</button></a>.
