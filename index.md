---
title: Containers and Workflows in Bioinformatics
author: CSC Training
---

# Course material for _Containers and Workflows in Bioinformatics_ 

{% assign items = site.hands-on |  sort: "title" %}


## 1. Lecture: [Introduction to Nextflow](https://a3s.fi/CSC_training/Introduction_workflows.pdf)
{% for hands-on in items %}
{% if hands-on.topic == 'nextflow' %}
## [{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

## 2. Lecture: [Biocontainers](https://a3s.fi/CSC_training/Biocontainers.pdf)
{% for hands-on in items %}
{% if hands-on.topic == 'bioapplications' %}
## [{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

## 3. Lecture: [Nextflow with containers](https://a3s.fi/CSC_training/Workflows_singularity_containers.pdf)

{% for hands-on in items %}
{% if hands-on.topic == 'nextflow_container' %}
## [{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

   
