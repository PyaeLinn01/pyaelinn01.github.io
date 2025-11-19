---
permalink: /projects/
title: "Projects"
---

<style>
.pinned-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 16px; }
.pin-card { border: 1px solid #1f2937; border-radius: 12px; padding: 14px; background: #0d1117; color: #e5e7eb; box-shadow: inset 0 0 0 1px rgba(255,255,255,0.02); min-height: 150px; display: flex; flex-direction: column; }
.pin-head { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
.pin-title { display: flex; gap: 8px; align-items: center; }
.pin-title a { color: #58a6ff; font-weight: 600; text-decoration: none; }
.pin-title a:hover { text-decoration: underline; }
.badge { border: 1px solid rgba(229,231,235,0.2); border-radius: 999px; padding: 1px 8px; font-size: 12px; color: #9ca3af; }
.pin-desc { flex: 1; font-size: 14px; color: #9ca3af; margin-bottom: 12px; }
.pin-meta { display: flex; gap: 14px; font-size: 12px; color: #9ca3af; }
.lang-dot { width: 12px; height: 12px; border-radius: 50%; display: inline-block; margin-right: 6px; background: #9ca3af; }
@media (prefers-color-scheme: light) {
  .pin-card { background: #fff; color: #111827; border-color: #e5e7eb; }
  .pin-title a { color: #0366d6; }
  .badge { color: #6b7280; border-color: #d1d5db; }
  .pin-desc { color: #4b5563; }
  .pin-meta { color: #6b7280; }
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
<\/script>
