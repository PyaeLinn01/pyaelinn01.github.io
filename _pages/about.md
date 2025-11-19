---
permalink: /
title: "Pyae Linn"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<style>
.hero { display: grid; grid-template-columns: 1.2fr 2fr; gap: 18px; align-items: center; padding: 20px; border: 1px solid #e5e7eb; border-radius: 16px; background: linear-gradient(135deg, #fdfbfb 0%, #ebedee 100%); box-shadow: 0 15px 45px rgba(15,23,42,0.15); }
.avatar { width: 120px; height: 120px; border-radius: 16px; object-fit: cover; border: 1px solid #e5e7eb; }
.title { font-size: 28px; font-weight: 700; margin: 0 0 6px; }
.subtitle { color: #6b7280; margin: 0 0 12px; }
.badges { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 10px; }
.badge { display: inline-flex; align-items: center; gap: 8px; padding: 8px 14px; border: 1px solid #d1d5db; border-radius: 999px; font-size: 13px; color: #111827; background: #ffffff; text-decoration: none; transition: transform .15s ease, box-shadow .15s ease; }
.badge i { color: #2563eb; }
.badge:hover { transform: translateY(-1px); box-shadow: 0 6px 18px rgba(15,23,42,0.1); }
.section { margin-top: 22px; }
.section h2 { font-size: 18px; margin: 0 0 10px; }
.cards { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px,1fr)); gap: 12px; }
.card { border: 1px solid #e5e7eb; border-radius: 10px; padding: 12px 14px; background: #ffffff; }
.muted { color: #6b7280; }
@media (max-width: 720px) { .hero { grid-template-columns: 1fr; } .avatar { width: 100px; height: 100px; } }
</style>

{% assign avatar_path = site.author.avatar %}
{% if avatar_path contains "://" %}
  {% assign avatar_url = avatar_path %}
{% else %}
  {% assign avatar_url = site.baseurl | append: "/images/" | append: avatar_path %}
{% endif %}

<div class="hero">
  <div>
    <img class="avatar" src="{{ avatar_url }}" alt="{{ site.author.name }}" />
  </div>
  <div>
    <div class="title">{{ site.author.name }}</div>
    <div class="subtitle">AI & ML Engineer · MLOps · Researcher</div>
    <div class="muted">Yangon, Myanmar</div>
    <div class="badges">
      <a class="badge" href="mailto:{{ site.author.email }}"><i class="fas fa-envelope"></i> Email</a>
      <a class="badge" href="{{ site.author.uri }}" target="_blank" rel="noopener"><i class="fas fa-globe"></i> Website</a>
      <a class="badge" href="https://github.com/{{ site.author.github }}" target="_blank" rel="noopener"><i class="fab fa-github"></i> GitHub</a>
      <a class="badge" href="https://www.facebook.com/profile.php?id=100049110682203" target="_blank" rel="noopener"><i class="fab fa-facebook"></i> Facebook</a>
    </div>
  </div>
  <div style="grid-column: 1 / -1" class="muted">
    I am a Computer Science student with a strong foundation in core CS principles and a deep passion for Artificial Intelligence. I have hands-on experience in multiple AI projects, including a Fruit Freshness Detection system (Samsung Innovation Campus AI Hackathon 2024 Winner Project), a Mental Support Chatbot, a Skin Condition Detection system with personalized skincare advice, and an AI-powered warehouse management system for sales prediction and faulty product detection (Code2Career Hackathon 2024 Winner Project). In addition to AI, I work with Java, PHP, Python, C++, JavaScript, databases, and software engineering.
  </div>
</div>

<div class="section">
  <h2>Education & Training</h2>
  <div class="cards">
    <div class="card">
      <div><strong>University of Information Technology</strong></div>
      <div class="muted">Yangon, Myanmar/Burma</div>
    </div>
    <div class="card">
      <div><strong>Foundation of Generative AI</strong></div>
      <div class="muted">Udacity · California, United States</div>
    </div>
    <div class="card">
      <div><strong>Certificate in Computer and Data Science</strong></div>
      <div class="muted">MIT · Cambridge, United States</div>
    </div>
  </div>
</div>

<div class="section">
  <h2>Contact</h2>
  <div class="badges">
    <span class="badge"><i class="fas fa-birthday-cake"></i> DOB: 20/11/2003</span>
    <span class="badge"><i class="fas fa-flag"></i> Burmese (Myanmar)</span>
    <a class="badge" href="tel:+959420053538"><i class="fas fa-phone"></i> (+95) 9420053538</a>
    <span class="badge"><i class="fab fa-viber"></i> 09420053538</span>
    <a class="badge" href="mailto:{{ site.author.email }}"><i class="fas fa-envelope"></i> {{ site.author.email }}</a>
    <a class="badge" href="{{ site.author.uri }}" target="_blank" rel="noopener"><i class="fas fa-globe"></i> {{ site.author.uri | replace: 'https://','' }}</a>
    <a class="badge" href="https://www.facebook.com/profile.php?id=100049110682203" target="_blank" rel="noopener"><i class="fab fa-facebook"></i> facebook.com/…</a>
    <span class="badge"><i class="fas fa-map-marker-alt"></i> No.531, Lower Pazundaung Rd, Yangon</span>
  </div>
</div>
