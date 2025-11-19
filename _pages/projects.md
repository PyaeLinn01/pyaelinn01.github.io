---
permalink: /projects/
title: "Projects"
---

Below are my pinned GitHub repositories.

<div class="project-grid">
{% for repo in site.data.pinned.repos %}
  {% assign parts = repo | split: '/' %}
  {% assign owner = parts[0] %}
  {% assign name = parts[1] %}
  <a class="project-card" href="https://github.com/{{ repo }}" target="_blank" rel="noopener">
    <div class="project-card__title">{{ name }}</div>
    <div class="project-card__meta">
      <img alt="stars" src="https://img.shields.io/github/stars/{{ repo }}?style=social" />
      <img alt="issues" src="https://img.shields.io/github/issues/{{ repo }}?color=blue" />
    </div>
  </a>
{% endfor %}
</div>
- App: [facecare.streamlit.app](https://facecare.streamlit.app)

### Text to Image Generator
- Stable Diffusion-based text-to-image generator.
- Repo: [github.com/PyaeLinn01/Text-to-Image-Generator](https://github.com/PyaeLinn01/Text-to-Image-Generator)

### One Fashion Shop Website Design
- E-commerce website design with product pages, cart, and checkout.
- Repo: [github.com/PyaeLinn01/One-Fashion-Shop-Website-Design](https://github.com/PyaeLinn01/One-Fashion-Shop-Website-Design)
- Live: [pyaelinn01.github.io/One-Fashion-Shop-Website-Design](https://pyaelinn01.github.io/One-Fashion-Shop-Website-Design/)

### HealthCare System JEE Web Application
- Data Structures and Algorithms with Java project: hospital management system & online booking.
- Repo: [github.com/PyaeLinn01/HealthCare-System-JEE](https://github.com/PyaeLinn01/HealthCare-System-JEE)

### Auto Water Pump
- Arduino and C++ project for automatic water pump control.
- Repo: [github.com/PyaeLinn01/Auto_Water_Pump](https://github.com/PyaeLinn01/Auto_Water_Pump)

### ExpressoButterCup
- PHP website design for a coffee shop.
- Repo: [github.com/PyaeLinn01/Coffee_Shop_Website](https://github.com/PyaeLinn01/Coffee_Shop_Website)
