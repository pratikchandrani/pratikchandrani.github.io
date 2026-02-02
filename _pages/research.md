---
layout: page
title: Research
permalink: /research/
---

## Overview

The Chandrani Lab focuses on computational biology and bioinformatics research to advance our understanding of cancer biology. We develop and apply cutting-edge computational methods to analyze large-scale genomic and clinical data, with the goal of improving cancer diagnosis, prognosis, and treatment.

### Research Areas

#### Cancer Genomics & Precision Medicine

We perform comprehensive genomic profiling of various cancer types to identify actionable alterations that can guide treatment decisions. Our work on EGFR mutations, ALK fusions, and other driver alterations in lung cancer has directly impacted clinical practice in India.

Key achievements:
- Development of **ClinOme**, a precision medicine solution that has been successfully technology-transferred
- Genomic characterization of over 3,000 cancer patients across multiple tumor types
- Identification of novel therapeutic targets and biomarkers for treatment response

#### Integrative Multi-Omics Analysis

We integrate data from multiple molecular layers (genomics, transcriptomics, proteomics) to gain comprehensive insights into cancer biology. Our approaches help identify:
- Molecular subtypes of cancers with distinct clinical outcomes
- Mechanisms of drug resistance
- Novel therapeutic vulnerabilities

#### Bioinformatics Pipeline Development

We develop robust, clinically-validated bioinformatics pipelines for:
- Next-generation sequencing (NGS) data analysis
- Variant calling and annotation
- Tumor mutation burden assessment
- Fusion detection from RNA-seq data
- Liquid biopsy analysis using cell-free DNA

#### Tumor Microenvironment & Host Factors

Beyond tumor-intrinsic alterations, we investigate:
- Microbiome associations with cancer (e.g., Fusobacterium in tongue cancer)
- Immune microenvironment profiling
- Host germline variants influencing cancer susceptibility and treatment response

---

## Recent Publications

{% assign recent_pubs = site.data.publications | slice: 0, 10 %}

<div class="publications-list">
{% for pub in recent_pubs %}
  {% include components/publication-item.html %}
{% endfor %}
</div>

<p class="text-center mt-4">
  <a href="/publications" class="btn btn-primary">View All Publications</a>
</p>

---

## Collaborations

We actively collaborate with clinicians, pathologists, and researchers at:
- Tata Memorial Centre
- Advanced Centre for Treatment, Research and Education in Cancer (ACTREC)
- National and international cancer research institutions

---

## Funding & Support

Our research is supported by:
- Department of Atomic Energy (DAE), Government of India
- Tata Memorial Centre
- Collaborative research grants

---

## Contact

Interested in collaborating or learning more about our research?

**Location:**
KS-121, ACTREC
Tata Memorial Centre
Kharghar, Navi Mumbai
India

For research inquiries, please contact us through our [application form](https://forms.gle/GmnGxzb7Axzfgirg6).
