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
      <li class="active">Refereed Articles</li>
      <li>Proceedings</li>
      <li>Invited Talks</li>
      <li>Published Software</li>
      <li>Data</li>
    </ul>
  </aside>

  <section class="pub-right">
    <h1>Refereed Articles</h1>
    <p class="pub-sub">Journal articles and preprints</p>

    <div class="pub-list">
      {% bibliography %}
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
      articles: {
        title: 'Refereed Articles',
        subtitle: 'Journal articles and preprints'
      },
      proceedings: {
        title: 'Proceedings',
        subtitle: 'Conference and symposium papers'
      }
    };

    function getVisibleSection() {
      return sections.find((s) => !s.hidden);
    }

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

    function switchSection(target) {
      sections.forEach((section) => {
        section.hidden = section.dataset.section !== target;
      });
      navButtons.forEach((btn) => {
        btn.classList.toggle('active', btn.dataset.target === target);
      });
      sectionTitle.textContent = sectionMeta[target].title;
      sectionSubtitle.textContent = sectionMeta[target].subtitle;
      fillYearOptions();
      applyYearFilter();
    }

    navButtons.forEach((btn) => {
      btn.addEventListener('click', () => switchSection(btn.dataset.target));
    });

    yearSelect.addEventListener('change', applyYearFilter);

    switchSection('articles');
  });
</script>
