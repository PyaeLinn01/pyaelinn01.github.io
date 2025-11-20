---
permalink: /skills/
title: "Skills"
---

<style>
.skills-grid { display: grid; grid-template-columns: repeat(auto-fit,minmax(220px,1fr)); gap: 20px; margin-top: 16px; }
.skill-card { position: relative; border-radius: 18px; padding: 20px; border: 1px solid rgba(148,163,184,.3); background: linear-gradient(135deg,#ffffff,#f8fafc); box-shadow: 0 12px 30px rgba(15,23,42,0.12); transition: transform .25s ease, box-shadow .25s ease; overflow: hidden; }
.skill-card:after { content: ""; position: absolute; inset: 0; background: radial-gradient(circle at top right, rgba(59,130,246,.15), transparent 45%); opacity: 0; transition: opacity .25s ease; }
.skill-card > * { position: relative; z-index: 1; }
.skill-card:hover { transform: translateY(-6px); box-shadow: 0 28px 55px rgba(15,23,42,0.18); }
.skill-card:hover:after { opacity: 1; }
.skill-card h3 { margin: 0 0 12px; font-size: 18px; display: flex; align-items: center; gap: 8px; color: #0f172a; }
.skill-list { display: flex; flex-wrap: wrap; gap: 8px; margin: 0; padding: 0; list-style: none; }
.skill-chip { display: inline-flex; align-items: center; gap: 6px; padding: 8px 14px; border-radius: 999px; background: rgba(37,99,235,.08); color: #1d4ed8; font-size: 13px; font-weight: 600; text-transform: uppercase; letter-spacing: .04em; }
.skill-chip::before { content: ""; width: 8px; height: 8px; border-radius: 50%; background: currentColor; box-shadow: 0 0 0 3px rgba(37,99,235,.25); }
@media (max-width: 640px) {
  .skill-chip { font-size: 12px; }
}
</style>

<div class="skills-grid">
  <div class="skill-card">
    <h3><i class="fas fa-code"></i> Core Languages</h3>
    <ul class="skill-list">
      <li class="skill-chip">Python</li>
      <li class="skill-chip">Java</li>
      <li class="skill-chip">PHP</li>
      <li class="skill-chip">C++</li>
      <li class="skill-chip">JavaScript</li>
    </ul>
  </div>

  <div class="skill-card">
    <h3><i class="fas fa-globe"></i> Web & Backend</h3>
    <ul class="skill-list">
      <li class="skill-chip">HTML</li>
      <li class="skill-chip">CSS</li>
      <li class="skill-chip">Apache</li>
      <li class="skill-chip">PHP</li>
      <li class="skill-chip">MySQL</li>
      <li class="skill-chip">Java Servlets</li>
    </ul>
  </div>

  <div class="skill-card">
    <h3><i class="fas fa-robot"></i> AI / ML Stack</h3>
    <ul class="skill-list">
      <li class="skill-chip">TensorFlow</li>
      <li class="skill-chip">PyTorch</li>
      <li class="skill-chip">Keras</li>
      <li class="skill-chip">PyROOT</li>
      <li class="skill-chip">RDataFrame</li>
    </ul>
  </div>

  <div class="skill-card">
    <h3><i class="fas fa-cubes"></i> MLOps & Deployment</h3>
    <ul class="skill-list">
      <li class="skill-chip">MLOps</li>
      <li class="skill-chip">Docker</li>
      <li class="skill-chip">MLflow</li>
      <li class="skill-chip">CI/CD</li>
    </ul>
  </div>
</div>
