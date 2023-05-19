---
title: Containers and Workflows in Bioinformatics
author: CSC Training
---

# Course material for _Containers and Workflows in Bioinformatics_ 

{% assign items = site.hands-on |  sort: "title" %}


## Lecture-1: [Introduction to Nextflow](https://a3s.fi/CSC_training/Introduction_workflows.pdf)
## Tutorials and exercises
{% for hands-on in items %}
{% if hands-on.topic == 'nextflow' %}
[{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

## Lecture-2: [Biocontainers](https://a3s.fi/CSC_training/Biocontainers.pdf)
## Tutorials and exercises
{% for hands-on in items %}
{% if hands-on.topic == 'bioapplications' %}
1. [{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

## Lecture-3: [Nextflow with containers](https://a3s.fi/CSC_training/Workflows_singularity_containers.pdf)
## Tutorials and exercises

{% for hands-on in items %}
{% if hands-on.topic == 'nextflow_container' %}
[{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

   
