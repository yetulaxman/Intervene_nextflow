---
title: Containers and Workflows in Bioinformatics
author: CSC Training
---

# Course material for _Containers and Workflows in Bioinformatics_ 

{% assign items = site.hands-on |  sort: "title" %}


## [Introduction to Nextflow]
### 3.[Introduction to Nextflow](https://a3s.fi/CSC_training/Introduction_workflows.pdf)
### 3.[Hello-world example](https://yetulaxman.github.io/containers-workflows/hands-on/day4/hello-world-nextflow.html)
### 3.FastQC example] (https://yetulaxman.github.io/containers-workflows/hands-on/day4/fastqc_nextflow.html)
### 4. [Biocontainers](Biocontainers.pdf](https://a3s.fi/CSC_training/Biocontainers.pdf)
{% for hands-on in items %}
{% if hands-on.topic == 'singularity' %}
1. [{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

### 4.1 [Nextflow with containers](Nextflow_singularity_containers.pdf](https://a3s.fi/CSC_training/Workflows_singularity_containers.pdf)
### 4.2 [Nextflow with containers](https://a3s.fi/CSC_training/Workflows_singularity_containers.pdf)
### [Run nf-core pipeline with hyperqueue executor](https://yetulaxman.github.io/containers-workflows/hands-on/day4/nf-core-hyperqueue.html)
### 4.3 Tutorials and exercises
{% for hands-on in items %}
{% if hands-on.topic == 'nextflow' %}
[{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

   
