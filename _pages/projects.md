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
  <a class="project-card" href="https://github.com/{{ repo }}" target="_blank" rel="noopener" data-repo="{{ repo }}">
    <div class="project-card__header">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" width="16" class="octicon">
        <path d="M2 2.5A2.5 2.5 0 0 1 4.5 0h7A2.5 2.5 0 0 1 14 2.5v11a.5.5 0 0 1-.757.429L8 10.101l-5.243 3.828A.5.5 0 0 1 2 13.5z"></path>
      </svg>
      <span class="project-card__name">{{ owner }}/<strong>{{ name }}</strong></span>
    </div>
    <div class="project-card__desc" data-desc>Loading description…</div>
    <div class="project-card__meta" data-meta>
      <span class="meta-item" data-language></span>
      <span class="meta-item" title="Stars" data-stars>★ --</span>
      <span class="meta-item" title="Forks" data-forks>⑂ --</span>
    </div>
  </a>
{% endfor %}
</div>

<script>
  document.addEventListener('DOMContentLoaded', async () => {
    const cards = document.querySelectorAll('.project-card');
    for (const card of cards) {
      const repo = card.getAttribute('data-repo');
      try {
        const res = await fetch(`https://api.github.com/repos/${repo}`);
        if (!res.ok) continue;
        const data = await res.json();
        const desc = card.querySelector('[data-desc]');
        const lang = card.querySelector('[data-language]');
        const stars = card.querySelector('[data-stars]');
        const forks = card.querySelector('[data-forks]');
        if (desc) desc.textContent = data.description || 'No description provided.';
        if (lang && data.language) lang.textContent = data.language;
        if (stars) stars.textContent = `★ ${data.stargazers_count}`;
        if (forks) forks.textContent = `⑂ ${data.forks_count}`;
      } catch (e) {
        // ignore
      }
    }
  });
<\/script>
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
