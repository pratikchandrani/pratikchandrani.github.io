---
layout: page
title: Publications
subtitle: Complete list of publications from the Chandrani Lab
permalink: /publications/
---

## All Publications

Our research has resulted in {{ site.data.publications.size }} publications in peer-reviewed journals, covering topics in cancer genomics, computational biology, precision medicine, and bioinformatics.

---

<div class="publications-list">
{% for pub in site.data.publications %}
  {% include components/publication-item.html %}
{% endfor %}
</div>

---

## Publication Metrics

For detailed publication metrics and citation information, please visit:

- [Google Scholar Profile](https://scholar.google.com/citations?user={{ site.scholar_id }})
- [PubMed Author Search](https://pubmed.ncbi.nlm.nih.gov/?term=Chandrani+P)

---

## Collaborations

Our publications reflect strong collaborations with:
- Clinical oncologists at Tata Memorial Centre
- Pathologists and molecular biologists at ACTREC
- National and international research institutions
- Industry partners for technology development

If you're interested in collaborating with us, please [get in touch](https://forms.gle/GmnGxzb7Axzfgirg6).
