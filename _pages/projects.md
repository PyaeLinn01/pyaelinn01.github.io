---
permalink: /projects/
title: "Projects"
---

<style>
.pinned-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 18px; }
.pin-card { position: relative; border: 1px solid rgba(148,163,184,.35); border-radius: 16px; padding: 18px; background: linear-gradient(145deg,#ffffff,#f8fafc); color: #1f2933; box-shadow: 0 10px 30px rgba(15,23,42,0.12); min-height: 150px; display: flex; flex-direction: column; gap: 10px; transition: transform .2s ease, box-shadow .2s ease; overflow: hidden; }
.pin-card:after { content: ""; position: absolute; inset: 0; background: radial-gradient(circle at top right, rgba(59,130,246,.15), transparent 40%); opacity: 0; transition: opacity .2s ease; }
.pin-card:hover { transform: translateY(-6px); box-shadow: 0 25px 45px rgba(15,23,42,0.18); }
.pin-card:hover:after { opacity: 1; }
.pin-card > * { position: relative; z-index: 1; }
.pin-head { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
.pin-title { display: flex; gap: 8px; align-items: center; }
.pin-title a { color: #0366d6; font-weight: 600; text-decoration: none; }
.pin-title a:hover { text-decoration: underline; }
.badge { border: 1px solid rgba(15,23,42,0.12); border-radius: 999px; padding: 1px 8px; font-size: 12px; color: #475569; background: #f8fafc; }
.pin-desc { flex: 1; font-size: 14px; color: #475569; margin-bottom: 12px; }
.pin-meta { display: flex; gap: 14px; font-size: 12px; color: #94a3b8; }
.lang-dot { width: 12px; height: 12px; border-radius: 50%; display: inline-block; margin-right: 6px; background: #0ea5e9; }
@media (prefers-color-scheme: light) {
  .pin-card { background: #ffffff; color: #111827; border-color: #e2e8f0; box-shadow: 0 4px 16px rgba(15,23,42,0.08); }
  .badge { color: #475569; border-color: #cbd5f5; }
  .pin-desc { color: #475569; }
  .pin-meta { color: #94a3b8; }
}
@media (prefers-color-scheme: dark) {
  .pin-card { background: #0f172a; border-color: #1f2937; color: #e5e7eb; box-shadow: inset 0 0 0 1px rgba(255,255,255,0.05); }
  .pin-title a { color: #58a6ff; }
  .badge { background: rgba(148,163,184,0.15); color: #cbd5f5; border-color: rgba(148,163,184,0.35); }
  .pin-desc { color: #cbd5f5; }
  .pin-meta { color: #94a3b8; }
  .lang-dot { background: #93c5fd; }
}
</style>

<div class="pinned-grid">
{% for repo in site.data.pinned.repos %}
  {% assign parts = repo | split: '/' %}
  {% assign owner = parts[0] %}
  {% assign name = parts[1] %}
  <a class="pin-card" href="https://github.com/{{ repo }}" target="_blank" rel="noopener" data-repo="{{ repo }}">
    <div class="pin-head">
      <div class="pin-title">
        <svg aria-hidden="true" height="16" viewBox="0 0 16 16" width="16" fill="currentColor"><path d="M2 2.5A2.5 2.5 0 0 1 4.5 0h7A2.5 2.5 0 0 1 14 2.5v11a.5.5 0 0 1-.757.429L8 10.101l-5.243 3.828A.5.5 0 0 1 2 13.5z"></path></svg>
        <span>{{ owner }}/<strong>{{ name }}</strong></span>
      </div>
      <span class="badge">Public</span>
    </div>
    <div class="pin-desc" data-desc>Loading description…</div>
    <div class="pin-meta">
      <span class="meta-lang" data-language><span class="lang-dot"></span></span>
      <span data-stars>★ --</span>
      <span data-forks>⑂ --</span>
      <span class="hide-sm" data-updated></span>
    </div>
  </a>
{% endfor %}
</div>

<script>
  document.addEventListener('DOMContentLoaded', async () => {
    const cards = document.querySelectorAll('.pin-card');
    for (const card of cards) {
      const repo = card.getAttribute('data-repo');
      try {
        const res = await fetch(`https://api.github.com/repos/${repo}`);
        if (!res.ok) continue;
        const d = await res.json();
        const desc = card.querySelector('[data-desc]');
        const lang = card.querySelector('[data-language]');
        const stars = card.querySelector('[data-stars]');
        const forks = card.querySelector('[data-forks]');
        const updated = card.querySelector('[data-updated]');
        if (desc) desc.textContent = d.description || 'No description provided.';
        if (lang && d.language) lang.innerHTML = `<span class="lang-dot"></span>${d.language}`;
        if (stars) stars.textContent = `★ ${d.stargazers_count}`;
        if (forks) forks.textContent = `⑂ ${d.forks_count}`;
        if (updated && d.updated_at) updated.textContent = new Date(d.updated_at).toLocaleDateString();
      } catch (_) {}
    }
  });
</script>

