---
layout: page
title: Photography
permalink: /photography/
cover: camera.jpg
last_modified_at: 2020-05-12
image: /assets/img/pratik_chandrani.png
---

<p class="mb-5">
  I have been keen on photography since 2017.
  I mostly take pictures of the scences in front of my eyes! It mostly includes wilflife, landscape, streets, light experiments, portraits and, astronomical objects.
  
  A few of my pictures can be found on
  <a href="https://www.instagram.com/pratikchandrani/">Instagram</a>.
  Here are some of my favorite shots.
</p>

{%- for picture in site.data.pictures -%}
  <div class='pixels-photo'>
    <p>
      <img src='{{ picture.url }}' alt='{{ picture.title }}'>
    </p>
  </div>

  <p class="font-weight-bold mb-5">
    {{ picture.title }}. {{ picture.location }} ({{ picture.year}})
  </p>
{%- endfor -%}
