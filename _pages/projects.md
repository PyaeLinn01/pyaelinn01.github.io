permalink: /projects/
title: "Projects"
---

<style>
/* ===== PROJECTS PAGE - MODERN, DARK-MODE AWARE ===== */
.projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; margin-top: 8px; }

.project-card {
  position: relative;
  border: 1px solid var(--global-border-color);
  border-radius: 18px;
  padding: 18px 18px 16px;
  background: var(--global-bg-color);
  box-shadow: 0 15px 40px rgba(0,0,0,0.12);
  display: flex;
  flex-direction: column;
  gap: 12px;
  overflow: hidden;
  transition: transform .25s ease, box-shadow .25s ease, border-color .25s ease;
}

.project-card::before {
  content: "";
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at 80% 0%, rgba(99,102,241,0.18), transparent 45%),
              radial-gradient(circle at 20% 20%, rgba(14,165,233,0.12), transparent 40%);
  opacity: 0;
  transition: opacity .25s ease;
}

.project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 25px 55px rgba(0,0,0,0.2);
  border-color: #6366f1;
}

.project-card:hover::before { opacity: 1; }
.project-card > * { position: relative; z-index: 1; }

.project-head { display: flex; align-items: center; justify-content: space-between; gap: 10px; }
.project-title { display: flex; align-items: center; gap: 8px; font-weight: 700; color: var(--global-text-color); }
.project-title a { color: #818cf8; text-decoration: none; }
.project-title a:hover { color: #a5b4fc; text-decoration: underline; }

.project-badge { padding: 4px 10px; border-radius: 999px; font-size: 12px; font-weight: 700; letter-spacing: .03em; background: rgba(99,102,241,0.15); color: #818cf8; border: 1px solid rgba(99,102,241,0.3); }

.project-desc { color: var(--global-text-color); font-size: 14px; line-height: 1.55; min-height: 48px; }

.project-meta { display: flex; flex-wrap: wrap; gap: 10px; font-size: 12px; color: var(--global-text-color-light); }
.meta-pill { display: inline-flex; align-items: center; gap: 6px; padding: 6px 10px; border-radius: 12px; background: rgba(148,163,184,0.15); color: var(--global-text-color); font-weight: 600; }
.meta-pill .dot { width: 10px; height: 10px; border-radius: 50%; background: #60a5fa; box-shadow: 0 0 0 4px rgba(96,165,250,0.2); }
.meta-pill i { color: #94a3b8; }

.updated { margin-left: auto; opacity: .8; }

/* Loading shimmer */
.skeleton { position: relative; color: transparent; }
.skeleton::after { content: ""; position: absolute; inset: 0; background: linear-gradient(90deg, transparent, rgba(255,255,255,0.12), transparent); animation: shimmer 1.25s infinite; }
@keyframes shimmer { 0% { transform: translateX(-100%); } 100% { transform: translateX(100%); } }

@media (max-width: 640px) {
  .projects-grid { grid-template-columns: 1fr; }
}
</style>

<div class="projects-grid">
{% for repo in site.data.pinned.repos %}
  {% assign parts = repo | split: '/' %}
  {% assign owner = parts[0] %}
  {% assign name = parts[1] %}
  <a class="project-card" href="https://github.com/{{ repo }}" target="_blank" rel="noopener" data-repo="{{ repo }}">
    <div class="project-head">
      <div class="project-title">
        <svg aria-hidden="true" height="18" viewBox="0 0 16 16" width="18" fill="currentColor"><path d="M2 2.5A2.5 2.5 0 0 1 4.5 0h7A2.5 2.5 0 0 1 14 2.5v11a.5.5 0 0 1-.757.429L8 10.101l-5.243 3.828A.5.5 0 0 1 2 13.5z"></path></svg>
        <span>{{ owner }}/<strong>{{ name }}</strong></span>
      </div>
      <span class="project-badge">GitHub</span>
    </div>

    <div class="project-desc skeleton" data-desc>Loading description…</div>

    <div class="project-meta">
      <span class="meta-pill" data-language><span class="dot"></span><span>Language</span></span>
      <span class="meta-pill" data-stars><i class="fas fa-star"></i> --</span>
      <span class="meta-pill" data-forks><i class="fas fa-code-branch"></i> --</span>
      <span class="meta-pill updated" data-updated><i class="fas fa-clock"></i> --</span>
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
        if (!res.ok) throw new Error('GitHub API error');
        const d = await res.json();

        const desc = card.querySelector('[data-desc]');
        const lang = card.querySelector('[data-language]');
        const stars = card.querySelector('[data-stars]');
        const forks = card.querySelector('[data-forks]');
        const updated = card.querySelector('[data-updated]');

        if (desc) {
          desc.textContent = d.description || 'No description provided.';
          desc.classList.remove('skeleton');
        }
        if (lang) {
          const language = d.language || 'N/A';
          lang.innerHTML = `<span class="dot"></span><span>${language}</span>`;
        }
        if (stars) stars.innerHTML = `<i class="fas fa-star"></i> ${d.stargazers_count}`;
        if (forks) forks.innerHTML = `<i class="fas fa-code-branch"></i> ${d.forks_count}`;
        if (updated && d.updated_at) updated.innerHTML = `<i class="fas fa-clock"></i> ${new Date(d.updated_at).toLocaleDateString()}`;
      } catch (err) {
        const desc = card.querySelector('[data-desc]');
        if (desc) {
          desc.textContent = 'Unable to load from GitHub right now.';
          desc.classList.remove('skeleton');
        }
      }
    }
  });
</script>

