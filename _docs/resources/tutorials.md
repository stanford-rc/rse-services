---
title: Tutorials
---

# Tutorials

The following tutorials can help you with data collection. These are created on request, so if you need any help with customization or setting these
up, please don't hesitate to [reach out]({{ site.baseurl }}/support)

## Data Collection

{% for action in site.data.templates.data-collection %}
<p id="{{ action.title | slugify }}"><a href="{{ action.url }}" target="_blank"><strong>{{ action.title }}</strong></a>: {{ action.description }}</p>
{% endfor %}
<hr>

Please [let us know]({{ site.repo }}/issues/new) if you have a request for a new tutorial.
