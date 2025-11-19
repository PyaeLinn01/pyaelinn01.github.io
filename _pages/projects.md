---
permalink: /projects/
title: "Projects"
---

Below are my pinned GitHub repositories.

<style>
.proj-table { width: 100%; border-collapse: collapse; margin-top: 12px; }
.proj-table th, .proj-table td { padding: 10px 12px; border-bottom: 1px solid #e5e7eb; vertical-align: top; }
.proj-table th { text-align: left; font-weight: 600; color: #374151; }
.proj-repo { font-weight: 600; color: #0366d6; text-decoration: none; }
.proj-repo:hover { text-decoration: underline; }
.proj-desc { color: #6b7280; font-size: 0.95em; }
.proj-meta { color: #6b7280; font-size: 0.9em; display: flex; gap: 10px; align-items: center; }
.lang-dot { width: 10px; height: 10px; border-radius: 50%; display: inline-block; margin-right: 6px; background: #9ca3af; }
@media (max-width: 720px) {
  .hide-sm { display: none; }
}
</style>

<table class="proj-table">
  <thead>
    <tr>
      <th>Repository</th>
      <th>Description</th>
      <th class="hide-sm">Language</th>
      <th>Stars</th>
      <th class="hide-sm">Forks</th>
      <th class="hide-sm">Updated</th>
    </tr>
  </thead>
  <tbody>
  {% for repo in site.data.pinned.repos %}
    {% assign parts = repo | split: '/' %}
    {% assign owner = parts[0] %}
    {% assign name = parts[1] %}
    <tr data-repo="{{ repo }}">
      <td><a class="proj-repo" href="https://github.com/{{ repo }}" target="_blank" rel="noopener">{{ owner }}/<strong>{{ name }}</strong></a></td>
      <td class="proj-desc" data-desc>Loading description…</td>
      <td class="hide-sm" data-language></td>
      <td data-stars>--</td>
      <td class="hide-sm" data-forks>--</td>
      <td class="hide-sm" data-updated>--</td>
    </tr>
  {% endfor %}
  </tbody>
</table>

<script>
  document.addEventListener('DOMContentLoaded', async () => {
    const rows = document.querySelectorAll('tr[data-repo]');
    for (const row of rows) {
      const repo = row.getAttribute('data-repo');
      try {
        const res = await fetch(`https://api.github.com/repos/${repo}`);
        if (!res.ok) continue;
        const d = await res.json();
        const desc = row.querySelector('[data-desc]');
        const lang = row.querySelector('[data-language]');
        const stars = row.querySelector('[data-stars]');
        const forks = row.querySelector('[data-forks]');
        const updated = row.querySelector('[data-updated]');
        if (desc) desc.textContent = d.description || 'No description provided.';
        if (lang && d.language) lang.textContent = d.language;
        if (stars) stars.textContent = `★ ${d.stargazers_count}`;
        if (forks) forks.textContent = `⑂ ${d.forks_count}`;
        if (updated && d.updated_at) updated.textContent = new Date(d.updated_at).toLocaleDateString();
      } catch (_) {}
    }
  });
<\/script>
