---
permalink: /experience/
title: "Work Experience"
---

<style>
.xp-wrapper { margin-top: 10px; display: grid; gap: 28px; }
.xp-section { border: 1px solid #e5e7eb; border-radius: 18px; padding: 24px; background: linear-gradient(135deg,#ffffff 0%,#f8fafc 100%); box-shadow: 0 20px 60px rgba(15,23,42,0.1); }
.xp-section h2 { margin-top: 0; font-size: 22px; display: flex; align-items: center; gap: 10px; }
.xp-section h2 i { color: #2563eb; }
.xp-timeline { position: relative; margin-top: 18px; padding-left: 26px; }
.xp-timeline:before { content: ""; position: absolute; left: 8px; top: 4px; bottom: 4px; width: 2px; background: linear-gradient(180deg,#2563eb,#60a5fa); border-radius: 999px; }
.xp-item { position: relative; padding: 0 0 20px 18px; }
.xp-item:last-child { padding-bottom: 0; }
.xp-dot { position: absolute; left: -2px; top: 6px; width: 12px; height: 12px; border-radius: 50%; background: #2563eb; box-shadow: 0 0 0 4px #dbeafe; }
.xp-card { border: 1px solid #e2e8f0; border-radius: 14px; padding: 18px; background: #ffffff; transition: transform .2s ease, box-shadow .2s ease; }
.xp-card:hover { transform: translateY(-4px); box-shadow: 0 20px 35px rgba(15,23,42,0.15); }
.xp-role { font-size: 18px; font-weight: 600; margin: 0 0 4px; }
.xp-meta { color: #64748b; font-size: 14px; margin-bottom: 12px; display: flex; flex-wrap: wrap; gap: 12px; }
.xp-tags { display: flex; flex-wrap: wrap; gap: 8px; margin: 0; padding: 0; list-style: none; }
.xp-tag { padding: 6px 12px; border-radius: 999px; font-size: 12px; font-weight: 600; text-transform: uppercase; letter-spacing: .04em; background: #eef2ff; color: #4338ca; }
.xp-list { margin: 0; padding-left: 18px; color: #1f2937; }
.xp-list a { color: #2563eb; font-weight: 600; }
@media (max-width: 640px) {
  .xp-section { padding: 18px; }
  .xp-timeline { padding-left: 18px; }
  .xp-dot { left: -4px; }
}
</style>

<div class="xp-wrapper">
  <section class="xp-section">
    <h2><i class="fas fa-briefcase"></i> Work Experience</h2>
    <div class="xp-timeline">
      <div class="xp-item">
        <span class="xp-dot"></span>
        <article class="xp-card">
          <p class="xp-role">AI Engineer · Dinger</p>
          <div class="xp-meta">
            <span><i class="fas fa-calendar"></i> 22 Jul 2025 – Present</span>
            <span><i class="fas fa-location-dot"></i> Yangon, Myanmar</span>
          </div>
          <ul class="xp-list">
            <li>Building OCR Model for Myanmar Handwritten Language.</li>
            <li>Develop Agentic AI systems for financial document processing workflows.</li>
            <li>Owning NLP pipelines that power multilingual support chatbots for financial services.</li>
          </ul>
          <ul class="xp-tags">
            <li class="xp-tag">OCR</li>
            <li class="xp-tag">Computer Vision</li>
            <li class="xp-tag">NLP</li>
            <li class="xp-tag">Production AI</li>
          </ul>
        </article>
      </div>

      <div class="xp-item">
        <span class="xp-dot"></span>
        <article class="xp-card">
          <p class="xp-role">NLP/AI R&D Intern · Language Understanding Laboratory (LU Lab)</p>
          <div class="xp-meta">
            <span><i class="fas fa-calendar"></i> 07 Jun 2025 – Present</span>
            <span><i class="fas fa-building"></i> Remote · Yangon</span>
          </div>
          <ul class="xp-list">
            <li>Leading multilingual NLP research for myFoodQA, accepted at IINAE 2025 (iSAI-NLP).</li>
            <li>Collaborating with cross-lab teams to benchmark cultural reasoning models.</li>
          </ul>
          <ul class="xp-tags">
            <li class="xp-tag">Research</li>
            <li class="xp-tag">Multimodal</li>
            <li class="xp-tag">LU Lab</li>
          </ul>
          <p style="margin:10px 0 0;"><a href="https://www.linkedin.com/company/lu-lab-my/" target="_blank" rel="noopener"><i class="fab fa-linkedin"></i> Follow LU Lab</a></p>
        </article>
      </div>
    </div>
  </section>

  <section class="xp-section">
    <h2><i class="fas fa-hands-helping"></i> Volunteering</h2>
    <div class="xp-timeline">
      <div class="xp-item">
        <span class="xp-dot"></span>
        <article class="xp-card">
          <p class="xp-role">Machine Learning Instructor · Alex Snow School</p>
          <div class="xp-meta">
            <span><i class="fas fa-calendar"></i> 2024 – Present</span>
            <span><i class="fas fa-globe"></i> YouTube · Remote</span>
          </div>
          <ul class="xp-list">
            <li>Designing bilingual video lessons that demystify ML fundamentals.</li>
            <li>Hosting weekly Q&A sessions to mentor early-career engineers.</li>
          </ul>
          <p style="margin:12px 0 0;">
            Playlist: <a href="https://www.youtube.com/watch?v=bLObh5mQmCM&list=PLUfr6Xq1RHDg0XaeAivWYFbmkvlSiDS_7&index=1" target="_blank" rel="noopener">Machine Learning Foundations Series</a>
          </p>
        </article>
      </div>
    </div>
  </section>
</div>
