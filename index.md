---
title: Containers and Workflows in Bioinformatics
author: CSC Training
---

# Course material for _Containers and Workflows in Bioinformatics_ 

{% assign items = site.hands-on |  sort: "title" %}


## 3. Running Singularity on HPC Environment 
### 3.1 [Slides: Converting docker images to singularity images](https://a3s.fi/containers-workflows/docker2singularity.html)
### 3.2 [Slides: Building singularity container images](https://a3s.fi/containers-workflows/Building_Singularity_Containers.html)
### 3.3 Tutorials and exercises
{% for hands-on in items %}
{% if hands-on.topic == 'singularity' %}
1. [{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

## 4. Nextflow on HPC 
### 4.1 [Slides: Introduction to workflows with nextflow](https://a3s.fi/containers-workflows/Intro_workflows.pdf)
### 4.2 [Slides: Workflows with singularity containers](https://a3s.fi/containers-workflows/workflow_singularity_containers.pdf)
### 4.3 Tutorials and exercises
{% for hands-on in items %}
{% if hands-on.topic == 'nextflow' %}
[{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

   
