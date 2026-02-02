---
layout: page
title: People
permalink: /people/
---

## Principal Investigator

<div class="row mb-5">
  <div class="col-md-12">
    <div class="person-card">
      <div class="person-card-image">
        <img src="/assets/img/pratik_chandrani.png" alt="Dr. Pratik Chandrani" class="img-fluid rounded-circle">
      </div>
      <div class="person-card-content">
        <h3 class="person-name">Dr. Pratik Chandrani</h3>
        <p class="person-position">Assistant Professor & Principal Investigator</p>
        <div class="person-expertise">
          <span class="expertise-tag">Computational Biology</span>
          <span class="expertise-tag">Cancer Genomics</span>
          <span class="expertise-tag">Bioinformatics</span>
          <span class="expertise-tag">Precision Medicine</span>
        </div>
        <p class="person-bio">
          Dr. Pratik Chandrani leads the Computational Biology & Bioinformatics research group at ACTREC,
          Tata Memorial Centre. His research focuses on integrative genomics approaches to understand cancer
          biology and develop precision medicine solutions. He is the recipient of the Foundation Day Award
          for outstanding PhD thesis and has successfully technology-transferred the precision medicine
          solution 'ClinOme'.
        </p>
        <div class="person-links">
          <a href="mailto:pchandrani@actrec.gov.in" class="person-link" title="Email">
            <i class="fas fa-envelope"></i>
          </a>
          <a href="https://github.com/{{ site.github_username }}" class="person-link" title="GitHub" target="_blank">
            <i class="fab fa-github"></i>
          </a>
          <a href="https://linkedin.com/in/{{ site.linkedin_username }}" class="person-link" title="LinkedIn" target="_blank">
            <i class="fab fa-linkedin"></i>
          </a>
          <a href="https://scholar.google.com/citations?user={{ site.scholar_id }}" class="person-link" title="Google Scholar" target="_blank">
            <i class="fas fa-graduation-cap"></i>
          </a>
        </div>
      </div>
    </div>
  </div>
</div>

## Current Team Members

<div class="row">
{% for person in site.data.people.current %}
  <div class="col-md-6 col-lg-4">
    {% include components/person-card.html %}
  </div>
{% endfor %}
</div>

## Past Members

{% if site.data.people.past.size > 0 %}
<div class="row">
{% for person in site.data.people.past %}
  <div class="col-md-6 col-lg-4">
    {% include components/person-card.html %}
  </div>
{% endfor %}
</div>
{% else %}
<p class="text-muted">Information about past members will be updated soon.</p>
{% endif %}

---

## Join Our Team

We are always looking for motivated students and researchers to join our group. If you are passionate about computational biology, bioinformatics, and cancer research, we would love to hear from you!

### Open Positions

- **PhD Fellows** - For students interested in pursuing doctoral research in computational biology
- **Project Assistants** - For fresh graduates with background in biology, biotechnology, or computer science
- **Research Associates** - For experienced researchers with computational or wet-lab expertise

**Interested?** [Apply here](https://forms.gle/GmnGxzb7Axzfgirg6)

---

## Alumni Network

We maintain close connections with our alumni who have gone on to pursue successful careers in academia, industry, and healthcare. If you are an alumnus of the Chandrani Lab, we'd love to stay in touch!
