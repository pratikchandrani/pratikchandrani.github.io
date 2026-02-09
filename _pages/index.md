---
layout: home
title: Home
permalink: "/"
hero_video: /assets/video/digital_cell_v5_20260203.mp4
hero_title: Chandrani Lab
hero_subtitle: Computational Biology & Data Science
---

<div class="row align-items-center mb-5">
  <div class="col-md-8">
    <h2>About the Lab</h2>
    <p>
      Welcome to our lab at <a href="https://actrec.gov.in/" target="_blank">ACTREC, Tata Memorial Centre</a>.
      We are a computational biology and genomics research group focused on understanding cancer biology through
      integrative omics and data science approaches.
    </p>
    <p>
      Our research combines computational methods, artificial intelligence, and biological model systems to uncover
      molecular mechanisms of cancer and develop precision medicine solutions. We work at the intersection of genomics,
      bioinformatics, and clinical oncology to translate biological insights into actionable knowledge.
    </p>
  </div>
  <div class="col-md-4 text-center">
    <a href="/about-pi/">
      <img src="/assets/img/pratik_chandrani.png" alt="Dr. Pratik Chandrani" class="img-fluid rounded-circle" style="max-width: 200px;">
    </a>
    <h4 class="mt-3"><a href="/about-pi/" style="color: inherit; text-decoration: none;">Dr. Pratik Chandrani</a></h4>
    <p class="text-muted">Assistant Professor<br>Principal Investigator</p>
    <div class="mt-2">
      <a href="https://linkedin.com/in/{{ site.linkedin_username }}" class="mx-1" title="LinkedIn" target="_blank">
        <i class="fab fa-linkedin"></i>
      </a>
      <a href="https://scholar.google.com/citations?user={{ site.scholar_id }}" class="mx-1" title="Google Scholar" target="_blank">
        <i class="fas fa-graduation-cap"></i>
      </a>
    </div>
  </div>
</div>

---

<div class="section mb-5">
  <h2></h2>
  <div class="row">
  {% for person in site.data.people.current %}
    <div class="col-md-6 col-lg-4 mb-4">
      {% include components/person-card.html %}
    </div>
  {% endfor %}
  </div>
</div>

{% if site.data.people.past.size > 0 %}
---

<div class="section mb-5">
  <h2>Past Members</h2>
  <div class="row">
  {% for person in site.data.people.past %}
    <div class="col-md-6 col-lg-4 mb-4">
      {% include components/person-card.html %}
    </div>
  {% endfor %}
  </div>
</div>
{% endif %}

---

<div class="section mb-5 p-4" style="background-color: #f8fafc; border-left: 4px solid #2563eb; border-radius: 8px;">
  <h2>Join Our Team!</h2>
  <p class="lead">
    We are actively recruiting passionate students and researchers interested in computational biology,
    bioinformatics, and cancer genomics. If you're excited about applying computational approaches to
    solve fundamental questions in cancer biology, we'd love to hear from you!
  </p>

  <div class="row align-items-center mt-4">
    <div class="col-md-8">
      <h4>Positions Available:</h4>
      <ul>
        <li><strong>PhD Fellows:</strong> For students interested in pursuing doctoral research</li>
        <li><strong>Project Assistants:</strong> For fresh graduates interested in bioinformatics</li>
        <li><strong>Research Associates:</strong> For experienced researchers with computational background</li>
      </ul>
      <p>
        <a href="https://forms.gle/GmnGxzb7Axzfgirg6" class="btn btn-primary btn-lg mt-3" target="_blank">
          Apply Now
        </a>
      </p>
    </div>
    <div class="col-md-4 text-center">
      <p class="mb-2"><strong>Scan to Apply</strong></p>
      <img src="/assets/img/PC_group_GoogleForms_QR_20260209.png" alt="Application QR Code" class="img-fluid" style="max-width: 200px;">
    </div>
  </div>
</div>

<div class="section">
  <h2>Connect With Us</h2>
  <p>Stay updated with our latest research and opportunities:</p>
  {%- include components/social.html -%}
</div>
