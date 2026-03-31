---
layout: page
permalink: /publications/
title: publications
nav: true
nav_order: 4
description: Refereed articles, proceedings, invited talks, software, and datasets.
---

<div class="pub-shell glass-card">
  <aside class="pub-left">
    <div class="pub-pill">🟢 Home • Publications</div>
    <h3>Publication Archive</h3>
    <ul class="pub-nav">
      <li><button type="button" class="pub-nav-btn active" data-target="articles">Refereed Articles</button></li>
      <li><button type="button" class="pub-nav-btn" data-target="proceedings">Proceedings</button></li>
    </ul>
  </aside>

  <section class="pub-right">
    <div class="pub-header-row">
      <div>
        <h1 id="pub-section-title">Refereed Articles</h1>
        <p class="pub-sub" id="pub-section-subtitle">Journal articles and preprints</p>
      </div>
      <label class="pub-year-filter" for="pub-year-select">
        <span>Year</span>
        <select id="pub-year-select">
          <option value="all">All Years</option>
        </select>
      </label>
    </div>

    <div class="pub-list" data-section="articles">
      {% bibliography --query @article %}
    </div>

    <div class="pub-list" data-section="proceedings" hidden>
      {% bibliography --query @inproceedings %}
    </div>
  </section>
</div>

<script>
  document.addEventListener('DOMContentLoaded', function () {
    const navButtons = Array.from(document.querySelectorAll('.pub-nav-btn'));
    const sections = Array.from(document.querySelectorAll('.pub-list[data-section]'));
    const yearSelect = document.getElementById('pub-year-select');
    const sectionTitle = document.getElementById('pub-section-title');
    const sectionSubtitle = document.getElementById('pub-section-subtitle');

    const sectionMeta = {
      articles: { title: 'Refereed Articles', subtitle: 'Journal articles and preprints' },
      proceedings: { title: 'Proceedings', subtitle: 'Conference and symposium papers' }
    };

    function getVisibleSection() { return sections.find((s) => !s.hidden); }

    function collectYears(section) {
      const years = Array.from(section.querySelectorAll('h2.year')).map((h) => h.textContent.trim());
      return [...new Set(years)].sort((a, b) => Number(b) - Number(a));
    }

    function fillYearOptions() {
      const section = getVisibleSection();
      const years = collectYears(section);
      const prevValue = yearSelect.value;
      yearSelect.innerHTML = '<option value="all">All Years</option>';
      years.forEach((year) => {
        const opt = document.createElement('option');
        opt.value = year;
        opt.textContent = year;
        yearSelect.appendChild(opt);
      });
      yearSelect.value = years.includes(prevValue) ? prevValue : 'all';
    }

    function applyYearFilter() {
      const section = getVisibleSection();
      const selected = yearSelect.value;
      const yearHeaders = Array.from(section.querySelectorAll('h2.year'));
      yearHeaders.forEach((header) => {
        const year = header.textContent.trim();
        const list = header.nextElementSibling;
        if (!list || !list.classList.contains('bibliography')) return;
        const show = selected === 'all' || selected === year;
        header.style.display = show ? '' : 'none';
        list.style.display = show ? '' : 'none';
      });
    }
    function cleanBrokenAuthorText() {
  document.querySelectorAll('.pub-list .bibliography li .author').forEach((el) => {
    el.innerHTML = el.innerHTML
      .replace(/var\s+cursorPosition[\s\S]*$/i, '')
      .replace(/setInterval\([\s\S]*$/i, '')
      .replace(/clearInterval\([\s\S]*$/i, '')
      .replace(/'\);\s*>.*$/i, '')
      .replace(/->\s*\d+\s*more\s*authors?/i, '')
      .trim();
  });
}
    function runArticleEnhancements() {
  cleanBrokenAuthorText();
  highlightAuthorName();
  makeTitlesClickable();
  initScrollReveal();
}

    function switchSection(target) {
      sections.forEach((section) => { section.hidden = section.dataset.section !== target; });
      navButtons.forEach((btn) => { btn.classList.toggle('active', btn.dataset.target === target); });
      sectionTitle.textContent = sectionMeta[target].title;
      sectionSubtitle.textContent = sectionMeta[target].subtitle;
      fillYearOptions();
      applyYearFilter();
    }

    navButtons.forEach((btn) => btn.addEventListener('click', () => switchSection(btn.dataset.target)));
    yearSelect.addEventListener('change', applyYearFilter);
    switchSection('articles');
  });
</script>
