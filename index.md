---
title: Containers and Workflows in Bioinformatics
author: CSC Training
---

# Course material for _Containers and Workflows in Bioinformatics_ 

{% assign items = site.hands-on |  sort: "title" %}


## Lecture-1: [Introduction to Nextflow](https://a3s.fi/CSC_training/Introduction_workflows.pdf)
## Tutorials-1:[Hello-world example](https://yetulaxman.github.io/containers-workflows/hands-on/day4/hello-world-nextflow.html)  and [FastQC example(https://yetulaxman.github.io/containers-workflows/hands-on/day4/fastqc_nextflow.html)
## Lecture-2. [Biocontainers](https://a3s.fi/CSC_training/Biocontainers.pdf)
## Tutorials-2:
{% for hands-on in items %}
{% if hands-on.topic == 'singularity' %}
1. [{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

## Lecture-3:  [Nextflow with containers](https://a3s.fi/CSC_training/Workflows_singularity_containers.pdf)
### Tutorials-3:[nf-core pipeline](https://yetulaxman.github.io/containers-workflows/hands-on/day4/nf-core.html) and [Run nf-core pipeline with hyperqueue executor](https://yetulaxman.github.io/containers-workflows/hands-on/day4/nf-core-hyperqueue.html)
### 4.3 Tutorials and exercises
{% for hands-on in items %}
{% if hands-on.topic == 'nextflow' %}
[{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

   
