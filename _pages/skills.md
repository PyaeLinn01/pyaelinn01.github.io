---
permalink: /skills/
title: "Skills"
---

<style>
/* ===== SKILLS PAGE - MODERN UI ===== */
:root {
  --skill-primary: #6366f1;
  --skill-secondary: #8b5cf6;
  --skill-accent: #06b6d4;
  --skill-success: #10b981;
  --skill-warning: #f59e0b;
  --skill-glass: rgba(255, 255, 255, 0.03);
  --skill-border: rgba(255, 255, 255, 0.08);
}

.skills-hero {
  text-align: center;
  margin-bottom: 3rem;
  position: relative;
}

.skills-hero h2 {
  font-size: 1.1rem;
  font-weight: 500;
  color: var(--global-text-color-light);
  margin: 0;
  letter-spacing: 0.05em;
}

.skills-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 1.5rem;
  margin-top: 1rem;
}

/* ===== SKILL CARD ===== */
.skill-card {
  position: relative;
  border-radius: 20px;
  padding: 1.75rem;
  background: var(--global-bg-color);
  border: 1px solid var(--global-border-color);
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.06);
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
}

.skill-card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--card-accent, #6366f1), var(--card-accent-end, #8b5cf6));
  opacity: 0;
  transition: opacity 0.3s ease;
}

.skill-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.12);
  border-color: transparent;
}

.skill-card:hover::before {
  opacity: 1;
}

/* Card accent colors */
.skill-card.languages { --card-accent: #6366f1; --card-accent-end: #8b5cf6; }
.skill-card.web { --card-accent: #06b6d4; --card-accent-end: #0ea5e9; }
.skill-card.ai { --card-accent: #10b981; --card-accent-end: #34d399; }
.skill-card.mlops { --card-accent: #f59e0b; --card-accent-end: #fbbf24; }

/* ===== CARD HEADER ===== */
.card-header {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1.25rem;
}

.card-icon {
  width: 48px;
  height: 48px;
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.25rem;
  color: #fff;
  background: linear-gradient(135deg, var(--card-accent, #6366f1), var(--card-accent-end, #8b5cf6));
  box-shadow: 0 8px 16px rgba(99, 102, 241, 0.25);
  transition: transform 0.3s ease;
}

.skill-card:hover .card-icon {
  transform: scale(1.1) rotate(-5deg);
}

.card-title {
  margin: 0;
  font-size: 1.15rem;
  font-weight: 700;
  color: var(--global-text-color);
}

.card-subtitle {
  margin: 4px 0 0;
  font-size: 0.8rem;
  color: var(--global-text-color-light);
  font-weight: 400;
}

/* ===== SKILL ITEMS ===== */
.skill-items {
  display: flex;
  flex-direction: column;
  gap: 0.875rem;
}

.skill-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0.625rem 0;
  border-bottom: 1px solid var(--global-border-color);
  transition: all 0.2s ease;
}

.skill-item:last-child {
  border-bottom: none;
}

.skill-item:hover {
  padding-left: 8px;
}

.skill-name {
  display: flex;
  align-items: center;
  gap: 0.625rem;
  font-weight: 600;
  font-size: 0.9rem;
  color: var(--global-text-color);
}

.skill-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--card-accent, #6366f1), var(--card-accent-end, #8b5cf6));
  box-shadow: 0 0 8px var(--card-accent);
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; transform: scale(1); }
  50% { opacity: 0.7; transform: scale(1.2); }
}

.skill-level {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.level-bar {
  width: 60px;
  height: 6px;
  background: var(--global-border-color);
  border-radius: 999px;
  overflow: hidden;
}

.level-fill {
  height: 100%;
  border-radius: 999px;
  background: linear-gradient(90deg, var(--card-accent, #6366f1), var(--card-accent-end, #8b5cf6));
  transition: width 1s cubic-bezier(0.4, 0, 0.2, 1);
}

.level-text {
  font-size: 0.7rem;
  font-weight: 700;
  color: var(--global-text-color-light);
  min-width: 28px;
  text-align: right;
}

/* ===== SKILL TAGS (Alternative Layout) ===== */
.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-top: 0.5rem;
}

.skill-tag {
  display: inline-flex;
  align-items: center;
  gap: 0.375rem;
  padding: 0.5rem 0.875rem;
  background: var(--global-border-color);
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 600;
  color: var(--global-text-color);
  transition: all 0.25s ease;
  cursor: default;
}

.skill-tag:hover {
  background: linear-gradient(135deg, var(--card-accent, #6366f1), var(--card-accent-end, #8b5cf6));
  color: #fff;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(99, 102, 241, 0.3);
}

.skill-tag i {
  font-size: 0.9rem;
}

/* ===== STATS BAR ===== */
.stats-bar {
  display: flex;
  justify-content: space-around;
  margin-top: 1.25rem;
  padding-top: 1.25rem;
  border-top: 1px dashed var(--global-border-color);
}

.stat-item {
  text-align: center;
}

.stat-value {
  font-size: 1.5rem;
  font-weight: 800;
  background: linear-gradient(135deg, var(--card-accent, #6366f1), var(--card-accent-end, #8b5cf6));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.stat-label {
  font-size: 0.7rem;
  color: var(--global-text-color-light);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-top: 2px;
}

/* ===== RESPONSIVE ===== */
@media (max-width: 640px) {
  .skills-container {
    grid-template-columns: 1fr;
  }
  
  .skill-card {
    padding: 1.25rem;
  }
  
  .card-icon {
    width: 42px;
    height: 42px;
    font-size: 1.1rem;
  }
  
  .level-bar {
    width: 50px;
  }
}
</style>

<div class="skills-hero">
  <h2>💡 Technologies & Tools I Work With</h2>
</div>

<div class="skills-container">
  
  <!-- Core Languages -->
  <div class="skill-card languages">
    <div class="card-header">
      <div class="card-icon"><i class="fas fa-code"></i></div>
      <div>
        <h3 class="card-title">Core Languages</h3>
        <p class="card-subtitle">Programming foundations</p>
      </div>
    </div>
    <div class="skill-items">
      <div class="skill-item">
        <span class="skill-name"><span class="skill-dot"></span> Python</span>
        <div class="skill-level">
          <div class="level-bar"><div class="level-fill" style="width: 95%"></div></div>
          <span class="level-text">95%</span>
        </div>
      </div>
      <div class="skill-item">
        <span class="skill-name"><span class="skill-dot"></span> Java</span>
        <div class="skill-level">
          <div class="level-bar"><div class="level-fill" style="width: 85%"></div></div>
          <span class="level-text">85%</span>
        </div>
      </div>
      <div class="skill-item">
        <span class="skill-name"><span class="skill-dot"></span> C++</span>
        <div class="skill-level">
          <div class="level-bar"><div class="level-fill" style="width: 75%"></div></div>
          <span class="level-text">75%</span>
        </div>
      </div>
      <div class="skill-item">
        <span class="skill-name"><span class="skill-dot"></span> JavaScript</span>
        <div class="skill-level">
          <div class="level-bar"><div class="level-fill" style="width: 80%"></div></div>
          <span class="level-text">80%</span>
        </div>
      </div>
      <div class="skill-item">
        <span class="skill-name"><span class="skill-dot"></span> PHP</span>
        <div class="skill-level">
          <div class="level-bar"><div class="level-fill" style="width: 70%"></div></div>
          <span class="level-text">70%</span>
        </div>
      </div>
    </div>
    <div class="stats-bar">
      <div class="stat-item"><span class="stat-value">5</span><div class="stat-label">Languages</div></div>
      <div class="stat-item"><span class="stat-value">4+</span><div class="stat-label">Years</div></div>
    </div>
  </div>

  <!-- Web & Backend -->
  <div class="skill-card web">
    <div class="card-header">
      <div class="card-icon"><i class="fas fa-globe"></i></div>
      <div>
        <h3 class="card-title">Web & Backend</h3>
        <p class="card-subtitle">Full-stack development</p>
      </div>
    </div>
    <div class="skill-tags">
      <span class="skill-tag"><i class="fab fa-html5"></i> HTML5</span>
      <span class="skill-tag"><i class="fab fa-css3-alt"></i> CSS3</span>
      <span class="skill-tag"><i class="fas fa-server"></i> Apache</span>
      <span class="skill-tag"><i class="fab fa-php"></i> PHP</span>
      <span class="skill-tag"><i class="fas fa-database"></i> MySQL</span>
      <span class="skill-tag"><i class="fab fa-java"></i> Java Servlets</span>
      <span class="skill-tag"><i class="fas fa-flask"></i> Flask</span>
      <span class="skill-tag"><i class="fas fa-bolt"></i> REST APIs</span>
    </div>
    <div class="stats-bar">
      <div class="stat-item"><span class="stat-value">8</span><div class="stat-label">Technologies</div></div>
      <div class="stat-item"><span class="stat-value">10+</span><div class="stat-label">Projects</div></div>
    </div>
  </div>

  <!-- AI / ML Stack -->
  <div class="skill-card ai">
    <div class="card-header">
      <div class="card-icon"><i class="fas fa-brain"></i></div>
      <div>
        <h3 class="card-title">AI / ML Stack</h3>
        <p class="card-subtitle">Machine learning & deep learning</p>
      </div>
    </div>
    <div class="skill-items">
      <div class="skill-item">
        <span class="skill-name"><span class="skill-dot"></span> TensorFlow</span>
        <div class="skill-level">
          <div class="level-bar"><div class="level-fill" style="width: 90%"></div></div>
          <span class="level-text">90%</span>
        </div>
      </div>
      <div class="skill-item">
        <span class="skill-name"><span class="skill-dot"></span> PyTorch</span>
        <div class="skill-level">
          <div class="level-bar"><div class="level-fill" style="width: 88%"></div></div>
          <span class="level-text">88%</span>
        </div>
      </div>
      <div class="skill-item">
        <span class="skill-name"><span class="skill-dot"></span> Keras</span>
        <div class="skill-level">
          <div class="level-bar"><div class="level-fill" style="width: 92%"></div></div>
          <span class="level-text">92%</span>
        </div>
      </div>
      <div class="skill-item">
        <span class="skill-name"><span class="skill-dot"></span> OpenCV</span>
        <div class="skill-level">
          <div class="level-bar"><div class="level-fill" style="width: 78%"></div></div>
          <span class="level-text">78%</span>
        </div>
      </div>
      <div class="skill-item">
        <span class="skill-name"><span class="skill-dot"></span> Scikit-learn</span>
        <div class="skill-level">
          <div class="level-bar"><div class="level-fill" style="width: 75%"></div></div>
          <span class="level-text">75%</span>
        </div>
      </div>
    </div>
    <div class="stats-bar">
      <div class="stat-item"><span class="stat-value">5</span><div class="stat-label">Frameworks</div></div>
      <div class="stat-item"><span class="stat-value">3+</span><div class="stat-label">Years</div></div>
    </div>
  </div>

  <!-- MLOps & Deployment -->
  <div class="skill-card mlops">
    <div class="card-header">
      <div class="card-icon"><i class="fas fa-rocket"></i></div>
      <div>
        <h3 class="card-title">MLOps & Deployment</h3>
        <p class="card-subtitle">Production-ready ML pipelines</p>
      </div>
    </div>
    <div class="skill-tags">
      <span class="skill-tag"><i class="fas fa-cogs"></i> MLOps</span>
      <span class="skill-tag"><i class="fab fa-docker"></i> Docker</span>
      <span class="skill-tag"><i class="fas fa-chart-line"></i> MLflow</span>
      <span class="skill-tag"><i class="fas fa-sync-alt"></i> CI/CD</span>
      <span class="skill-tag"><i class="fab fa-github"></i> GitHub Actions</span>
      <span class="skill-tag"><i class="fas fa-cloud"></i> Cloud Deploy</span>
    </div>
    <div class="stats-bar">
      <div class="stat-item"><span class="stat-value">6</span><div class="stat-label">Tools</div></div>
      <div class="stat-item"><span class="stat-value">5+</span><div class="stat-label">Pipelines</div></div>
    </div>
  </div>

</div>
