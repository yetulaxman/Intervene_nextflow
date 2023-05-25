---
title: Training materials for Nextflow and containers 
author: CSC Training
---

{% assign items = site.hands-on |  sort: "title" %}


## 1. Session: [Introduction to Nextflow](https://a3s.fi/CSC_training/Introduction_workflows.pdf)
{% for hands-on in items %}
{% if hands-on.topic == 'nextflow' %}
## [{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

## 2. Session: [Primer on using containers in HPC environment](https://a3s.fi/CSC_training/Biocontainers.pdf)
{% for hands-on in items %}
{% if hands-on.topic == 'bioapplications' %}
## [{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

## 3. Session: [Nextflow with Singularity containers](https://a3s.fi/CSC_training/Workflows_singularity_containers.pdf)

{% for hands-on in items %}
{% if hands-on.topic == 'nextflow_container' %}
## [{{ hands-on.title }}]({{ hands-on.url | relative_url }})
{% endif %}
{% endfor %}

   
