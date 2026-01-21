---
permalink: /
title: "Pyae Linn"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<style>
/* ===== ABOUT PAGE - PREMIUM UI ===== */
:root {
  --about-primary: #6366f1;
  --about-secondary: #8b5cf6;
  --about-accent: #06b6d4;
  --about-success: #10b981;
  --about-glass: rgba(255, 255, 255, 0.7);
}

/* ===== HERO SECTION ===== */
.about-hero {
  position: relative;
  border-radius: 24px;
  padding: 2.5rem;
  background: var(--global-bg-color);
  border: 1px solid var(--global-border-color);
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.about-hero::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 6px;
  background: linear-gradient(90deg, #6366f1, #8b5cf6, #06b6d4, #10b981);
  background-size: 300% 100%;
  animation: gradientMove 4s ease infinite;
}

@keyframes gradientMove {
  0%, 100% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
}

.hero-grid {
  display: grid;
  grid-template-columns: auto 1fr;
  gap: 2rem;
  align-items: start;
}

/* ===== AVATAR ===== */
.avatar-wrapper {
  position: relative;
}

.avatar-glow {
  position: absolute;
  inset: -4px;
  border-radius: 24px;
  background: linear-gradient(135deg, #6366f1, #8b5cf6, #06b6d4);
  opacity: 0.6;
  filter: blur(12px);
  z-index: 0;
  animation: pulseGlow 3s ease-in-out infinite;
}

@keyframes pulseGlow {
  0%, 100% { opacity: 0.4; transform: scale(1); }
  50% { opacity: 0.7; transform: scale(1.02); }
}

.avatar-img {
  position: relative;
  width: 140px;
  height: 140px;
  border-radius: 20px;
  object-fit: cover;
  border: 4px solid var(--global-bg-color);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
  z-index: 1;
  transition: transform 0.4s ease;
}

.avatar-wrapper:hover .avatar-img {
  transform: scale(1.05) rotate(-2deg);
}

.status-badge {
  position: absolute;
  bottom: 8px;
  right: 8px;
  width: 20px;
  height: 20px;
  background: #10b981;
  border: 3px solid var(--global-bg-color);
  border-radius: 50%;
  z-index: 2;
  animation: statusPulse 2s ease infinite;
}

@keyframes statusPulse {
  0%, 100% { box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.4); }
  50% { box-shadow: 0 0 0 8px rgba(16, 185, 129, 0); }
}

/* ===== HERO CONTENT ===== */
.hero-content {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.hero-name {
  margin: 0;
  font-size: 2.25rem;
  font-weight: 800;
  background: linear-gradient(135deg, var(--global-text-color) 0%, var(--global-text-color) 50%, #6366f1 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  letter-spacing: -0.02em;
}

.hero-title {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 0.5rem;
  margin: 0;
  font-size: 1.1rem;
  font-weight: 500;
  color: var(--global-text-color-light);
}

.title-divider {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
}

.hero-location {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.9rem;
  color: var(--global-text-color-light);
}

.hero-location i {
  color: #ef4444;
}

/* ===== SOCIAL LINKS ===== */
.social-links {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  margin-top: 0.5rem;
}

.social-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  padding: 0.625rem 1.125rem;
  background: var(--global-border-color);
  border: none;
  border-radius: 12px;
  font-size: 0.875rem;
  font-weight: 600;
  color: var(--global-text-color);
  text-decoration: none;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  cursor: pointer;
}

.social-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
}

.social-btn.email:hover { background: linear-gradient(135deg, #ef4444, #f87171); color: #fff; }
.social-btn.website:hover { background: linear-gradient(135deg, #6366f1, #8b5cf6); color: #fff; }
.social-btn.github:hover { background: linear-gradient(135deg, #171717, #404040); color: #fff; }
.social-btn.linkedin:hover { background: linear-gradient(135deg, #0077b5, #00a0dc); color: #fff; }
.social-btn.facebook:hover { background: linear-gradient(135deg, #1877f2, #42a5f5); color: #fff; }

.social-btn i {
  font-size: 1rem;
}

/* ===== BIO SECTION ===== */
.bio-section {
  margin-top: 2rem;
  padding-top: 2rem;
  border-top: 1px dashed var(--global-border-color);
}

.bio-text {
  font-size: 1rem;
  line-height: 1.8;
  color: var(--global-text-color);
}

.bio-text .highlight {
  display: inline;
  padding: 0.125rem 0.5rem;
  background: linear-gradient(135deg, rgba(99, 102, 241, 0.1), rgba(139, 92, 246, 0.1));
  border-radius: 6px;
  font-weight: 600;
  color: #6366f1;
}

/* ===== ACHIEVEMENTS CHIPS ===== */
.achievements {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  margin-top: 1.25rem;
}

.achievement-chip {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem 1rem;
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.1), rgba(52, 211, 153, 0.1));
  border: 1px solid rgba(16, 185, 129, 0.2);
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 600;
  color: #059669;
}

.achievement-chip i {
  color: #10b981;
}

/* ===== SECTIONS ===== */
.about-section {
  margin-top: 2.5rem;
}

.section-header {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 1.25rem;
}

.section-icon {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 12px;
  font-size: 1.1rem;
  color: #fff;
}

.section-icon.education { background: linear-gradient(135deg, #6366f1, #8b5cf6); }
.section-icon.contact { background: linear-gradient(135deg, #06b6d4, #0ea5e9); }

.section-title {
  margin: 0;
  font-size: 1.35rem;
  font-weight: 700;
  color: var(--global-text-color);
}

/* ===== EDUCATION CARDS ===== */
.edu-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1rem;
}

.edu-card {
  position: relative;
  padding: 1.25rem 1.5rem;
  background: var(--global-bg-color);
  border: 1px solid var(--global-border-color);
  border-radius: 16px;
  transition: all 0.3s ease;
  overflow: hidden;
}

.edu-card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 4px;
  height: 100%;
  background: linear-gradient(180deg, #6366f1, #8b5cf6);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.edu-card:hover {
  transform: translateX(8px);
  border-color: #6366f1;
  box-shadow: 0 10px 30px rgba(99, 102, 241, 0.1);
}

.edu-card:hover::before {
  opacity: 1;
}

.edu-name {
  margin: 0 0 0.375rem;
  font-size: 1rem;
  font-weight: 700;
  color: var(--global-text-color);
}

.edu-location {
  display: flex;
  align-items: center;
  gap: 0.375rem;
  font-size: 0.85rem;
  color: var(--global-text-color-light);
}

.edu-location i {
  font-size: 0.75rem;
  color: #6366f1;
}

/* ===== CONTACT GRID ===== */
.contact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 0.875rem;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 0.875rem;
  padding: 1rem 1.25rem;
  background: var(--global-bg-color);
  border: 1px solid var(--global-border-color);
  border-radius: 14px;
  text-decoration: none;
  color: var(--global-text-color);
  transition: all 0.3s ease;
}

.contact-item:hover {
  border-color: #06b6d4;
  background: linear-gradient(135deg, rgba(6, 182, 212, 0.05), rgba(14, 165, 233, 0.05));
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(6, 182, 212, 0.1);
}

.contact-icon {
  width: 36px;
  height: 36px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 10px;
  background: linear-gradient(135deg, rgba(6, 182, 212, 0.1), rgba(14, 165, 233, 0.1));
  color: #06b6d4;
  font-size: 0.95rem;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 0.125rem;
  min-width: 0;
}

.contact-label {
  font-size: 0.7rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: var(--global-text-color-light);
}

.contact-value {
  font-size: 0.875rem;
  font-weight: 600;
  color: var(--global-text-color);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

/* ===== RESPONSIVE ===== */
@media (max-width: 640px) {
  .about-hero {
    padding: 1.5rem;
  }
  
  .hero-grid {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .avatar-wrapper {
    margin: 0 auto;
  }
  
  .avatar-img {
    width: 120px;
    height: 120px;
  }
  
  .hero-name {
    font-size: 1.75rem;
  }
  
  .hero-title {
    justify-content: center;
  }
  
  .hero-location {
    justify-content: center;
  }
  
  .social-links {
    justify-content: center;
  }
  
  .bio-section {
    text-align: left;
  }
  
  .achievements {
    justify-content: center;
  }
  
  .contact-grid {
    grid-template-columns: 1fr;
  }
}
</style>

{% assign avatar_path = site.author.avatar %}
{% if avatar_path contains "://" %}
  {% assign avatar_url = avatar_path %}
{% else %}
  {% assign avatar_url = site.baseurl | append: "/images/" | append: avatar_path %}
{% endif %}

<div class="about-hero">
  <div class="hero-grid">
    <!-- Avatar -->
    <div class="avatar-wrapper">
      <div class="avatar-glow"></div>
      <img class="avatar-img" src="{{ avatar_url }}" alt="{{ site.author.name }}" />
      <div class="status-badge" title="Available for opportunities"></div>
    </div>
    <!-- Hero Content -->
    <div class="hero-content">
      <h1 class="hero-name">{{ site.author.name }}</h1>
      <p class="hero-title">
        <span>AI & ML Engineer</span>
        <span class="title-divider"></span>
        <span>MLOps</span>
        <span class="title-divider"></span>
        <span>Researcher</span>
      </p>
      <span class="hero-location">
        <i class="fas fa-map-marker-alt"></i> Yangon, Myanmar
      </span>
      <!-- Social Links -->
      <div class="social-links">
        <a class="social-btn email" href="mailto:{{ site.author.email }}"><i class="fas fa-envelope"></i> Email</a>
        <a class="social-btn website" href="{{ site.author.uri }}" target="_blank" rel="noopener"><i class="fas fa-globe"></i> Website</a>
        <a class="social-btn github" href="https://github.com/{{ site.author.github }}" target="_blank" rel="noopener"><i class="fab fa-github"></i> GitHub</a>
        <a class="social-btn linkedin" href="https://www.linkedin.com/in/{{ site.author.linkedin }}" target="_blank" rel="noopener"><i class="fab fa-linkedin"></i> LinkedIn</a>
        <a class="social-btn facebook" href="https://www.facebook.com/profile.php?id=100049110682203" target="_blank" rel="noopener"><i class="fab fa-facebook"></i> Facebook</a>
      </div>
    </div>
  </div>
  
  <!-- Bio Section -->
  <div class="bio-section">
    <p class="bio-text">
      I am a <span class="highlight">Computer Science student</span> with a strong foundation in core CS principles and a deep passion for <span class="highlight">Artificial Intelligence</span>.
    </p>
    <p class="bio-text">
      I have hands-on experience in multiple AI projects, including a <span class="highlight">Fruit Freshness Detection</span> system, a <span class="highlight">Mental Support Chatbot</span>, a <span class="highlight">Skin Condition Detection</span> system with personalized skincare advice, and an <span class="highlight">AI-powered Warehouse Management</span> system for sales prediction and faulty product detection.
    </p>
    <p class="bio-text">
      Beyond AI, I work with Java, PHP, Python, C++, JavaScript, databases, and software engineering.
    </p>
    <!-- Achievement Chips -->
    <div class="achievements">
      <span class="achievement-chip"><i class="fas fa-trophy"></i> Samsung AI Hackathon 2024 Winner</span>
      <span class="achievement-chip"><i class="fas fa-award"></i> Code2Career Hackathon 2024 Winner</span>
    </div>
  </div>
</div>

<!-- Education Section -->
<div class="about-section">
  <div class="section-header">
    <div class="section-icon education"><i class="fas fa-graduation-cap"></i></div>
    <h2 class="section-title">Education & Training</h2>
  </div>
  <div class="edu-grid">
    <div class="edu-card">
      <h3 class="edu-name">University of Information Technology</h3>
      <span class="edu-location"><i class="fas fa-map-pin"></i> Yangon, Myanmar</span>
    </div>
    <div class="edu-card">
      <h3 class="edu-name">Certificate in Computer and Data Science</h3>
      <span class="edu-location"><i class="fas fa-map-pin"></i> MIT · Cambridge, United States</span>
    </div>
  </div>
</div>

<!-- Contact Section -->
<div class="about-section">
  <div class="section-header">
    <div class="section-icon contact"><i class="fas fa-paper-plane"></i></div>
    <h2 class="section-title">Get In Touch</h2>
  </div>
  <div class="contact-grid">
    <a class="contact-item" href="tel:+959420053538">
      <div class="contact-icon"><i class="fas fa-phone"></i></div>
      <div class="contact-info">
        <span class="contact-label">Phone</span>
        <span class="contact-value">(+95) 9420053538</span>
      </div>
    </a>
    <div class="contact-item">
      <div class="contact-icon"><i class="fab fa-viber"></i></div>
      <div class="contact-info">
        <span class="contact-label">Viber</span>
        <span class="contact-value">09420053538</span>
      </div>
    </div>
    <a class="contact-item" href="mailto:{{ site.author.email }}">
      <div class="contact-icon"><i class="fas fa-envelope"></i></div>
      <div class="contact-info">
        <span class="contact-label">Email</span>
        <span class="contact-value">{{ site.author.email }}</span>
      </div>
    </a>
    <a class="contact-item" href="{{ site.author.uri }}" target="_blank" rel="noopener">
      <div class="contact-icon"><i class="fas fa-globe"></i></div>
      <div class="contact-info">
        <span class="contact-label">Website</span>
        <span class="contact-value">{{ site.author.uri | replace: 'https://','' }}</span>
      </div>
    </a>
    <a class="contact-item" href="https://www.linkedin.com/in/{{ site.author.linkedin }}" target="_blank" rel="noopener">
      <div class="contact-icon"><i class="fab fa-linkedin"></i></div>
      <div class="contact-info">
        <span class="contact-label">LinkedIn</span>
        <span class="contact-value">{{ site.author.linkedin }}</span>
      </div>
    </a>
    <a class="contact-item" href="https://www.facebook.com/profile.php?id=100049110682203" target="_blank" rel="noopener">
      <div class="contact-icon"><i class="fab fa-facebook"></i></div>
      <div class="contact-info">
        <span class="contact-label">Facebook</span>
        <span class="contact-value">Pyae Linn</span>
      </div>
    </a>
    <div class="contact-item">
      </div>
    </div>
  </div>
</div>
