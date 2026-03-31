---
layout: page
permalink: /publications/
title: publications
nav: true
nav_order: 4
description: Refereed articles, proceedings, software, and datasets.
---

<div class="pub-shell glass-card">
  <aside class="pub-left">
    <div class="pub-pill">Home • Publications</div>
    <h3>Publication Archive</h3>

    <ul class="pub-nav">
      <li><button type="button" class="pub-nav-btn active" data-target="articles"><span>▶</span> Refereed Articles</button></li>
      <li><button type="button" class="pub-nav-btn" data-target="proceedings"><span>▶</span> Proceedings</button></li>
      <li><button type="button" class="pub-nav-btn" data-target="software"><span>▶</span> Published Software</button></li>
      <li><button type="button" class="pub-nav-btn" data-target="data"><span>▶</span> Published Data</button></li>
    </ul>
  </aside>

  <section class="pub-right">
    <div class="pub-header-row">
      <div>
        <h1 id="pub-section-title">Refereed Articles</h1>
        <p class="pub-sub" id="pub-section-subtitle">Journal articles and preprints</p>
      </div>

      <label class="pub-year-filter" for="pub-year-select" id="pub-year-wrap">
        <span>Year</span>
        <select id="pub-year-select">
          <option value="all">All Years</option>
        </select>
      </label>
    </div>

    <!-- Refereed Articles -->
    <div class="pub-list" data-section="articles">
      {% bibliography --query @article %}
    </div>

    <!-- Proceedings -->
    <div class="pub-list" data-section="proceedings" hidden>
      {% bibliography --query @inproceedings %}
    </div>

    <!-- Published Software -->
    <div class="pub-list" data-section="software" hidden>
      <ul class="bibliography">
        <li>
          <div class="title">Add your software title here</div>
          <div class="author">Your Name, Coauthors</div>
          <div class="periodical"><em>Year</em></div>
          <div class="links">
            <a href="#" target="_blank" rel="noopener">Code</a>
            <a href="#" target="_blank" rel="noopener">Docs</a>
            <a href="#" target="_blank" rel="noopener">DOI</a>
          </div>
        </li>
      </ul>
    </div>

    <!-- Published Data -->
    <div class="pub-list" data-section="data" hidden>
      <ul class="bibliography">
        <li>
          <div class="title">Add your dataset title here</div>
          <div class="author">Your Name, Coauthors</div>
          <div class="periodical"><em>Year</em></div>
          <div class="links">
            <a href="#" target="_blank" rel="noopener">Repository</a>
            <a href="#" target="_blank" rel="noopener">DOI</a>
            <a href="#" target="_blank" rel="noopener">Metadata</a>
          </div>
        </li>
      </ul>
    </div>
  </section>
</div>

<script>
  document.addEventListener('DOMContentLoaded', function () {
    const navButtons = Array.from(document.querySelectorAll('.pub-nav-btn'));
    const sections = Array.from(document.querySelectorAll('.pub-list[data-section]'));
    const yearSelect = document.getElementById('pub-year-select');
    const yearWrap = document.getElementById('pub-year-wrap');
    const sectionTitle = document.getElementById('pub-section-title');
    const sectionSubtitle = document.getElementById('pub-section-subtitle');

    const sectionMeta = {
      articles: {
        title: 'Refereed Articles',
        subtitle: 'Journal articles and preprints',
        yearFilter: true
      },
      proceedings: {
        title: 'Proceedings',
        subtitle: 'Conference and symposium papers',
        yearFilter: true
      },
      software: {
        title: 'Published Software',
        subtitle: 'Open-source tools and research software',
        yearFilter: false
      },
      data: {
        title: 'Published Data',
        subtitle: 'Datasets, catalogs, and archives',
        yearFilter: false
      }
    };

    function getVisibleSection() {
      return sections.find((s) => !s.hidden);
    }

    function collectYears(section) {
      // First try headings
      let years = Array.from(section.querySelectorAll('h2.year, h2, h3'))
        .map((el) => (el.textContent.match(/\b(19|20)\d{2}\b/) || [])[0])
        .filter(Boolean);

      // Fallback: scan whole section text
      if (years.length === 0) {
        const txt = section.textContent || '';
        years = txt.match(/\b(19|20)\d{2}\b/g) || [];
      }

      return [...new Set(years)].sort((a, b) => Number(b) - Number(a));
    }

    function fillYearOptions() {
      const section = getVisibleSection();
      const years = collectYears(section);
      const prevValue = yearSelect.value || 'all';

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

      // Works with bibliography output grouped by year headings
      const yearHeaders = Array.from(section.querySelectorAll('h2.year, h2, h3'));

      yearHeaders.forEach((header) => {
        const matchedYear = (header.textContent.match(/\b(19|20)\d{2}\b/) || [])[0];
        const list = header.nextElementSibling;

        if (!matchedYear || !list) return;

        const show = selected === 'all' || selected === matchedYear;
        header.style.display = show ? '' : 'none';
        list.style.display = show ? '' : 'none';
      });
    }
    function animateArticleCards() {
  const articleSection = document.querySelector('.pub-list[data-section="articles"]');
  if (!articleSection) return;
  const cards = Array.from(articleSection.querySelectorAll('.bibliography li'));

  cards.forEach((card, i) => {
    card.classList.remove('reveal-in');
    card.style.animationDelay = `${i * 110}ms`;
    void card.offsetWidth; // restart animation
    card.classList.add('reveal-in');
  });
}

function highlightAuthorName() {
  document.querySelectorAll('.pub-list .bibliography li .author').forEach((el) => {
    let html = el.innerHTML;

    // remove old full-name wraps if already applied
    html = html.replace(/<span class="me-highlight">(.*?)<\/span>/g, '$1');

    // highlight full name once (single border, no double look)
    html = html.replace(/Dibya Kirti Mishra/g, '<span class="me-highlight">Dibya Kirti Mishra</span>');

    // inside that, color only Kirti Mishra
    html = html.replace(/Kirti Mishra/g, '<span class="km-name">Kirti Mishra</span>');

    el.innerHTML = html;
  });
}


    function switchSection(target) {
      sections.forEach((section) => {
        section.hidden = section.dataset.section !== target;
      });
      if (target === 'articles') {
  highlightAuthorName();
  animateArticleCards();
}

      navButtons.forEach((btn) => {
        btn.classList.toggle('active', btn.dataset.target === target);
      });

      sectionTitle.textContent = sectionMeta[target].title;
      sectionSubtitle.textContent = sectionMeta[target].subtitle;

      if (sectionMeta[target].yearFilter) {
        yearWrap.style.display = '';
        fillYearOptions();
        applyYearFilter();
      } else {
        yearWrap.style.display = 'none';
      }
      // 👇 put it here
     if (target === 'articles') animateArticleCards();
    }

    navButtons.forEach((btn) => {
      btn.addEventListener('click', () => switchSection(btn.dataset.target));
    });

    yearSelect.addEventListener('change', applyYearFilter);

    switchSection('articles');
    highlightAuthorName();
    animateArticleCards();
  
  });
  function animateArticleCards() {
  const articleSection = document.querySelector('.pub-list[data-section="articles"]');
  if (!articleSection) return;

  const cards = Array.from(articleSection.querySelectorAll('.bibliography li'));
  cards.forEach((card, i) => {
    card.classList.remove('reveal-in');
    card.style.animationDelay = `${i * 90}ms`;
    void card.offsetWidth; // reflow for restart
    card.classList.add('reveal-in');
  });
}
</script>
<style>
  /* Hide page title + description only on publications page */
  .post-header .post-title,
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }

  /* optional: remove extra top gap after hiding */
  .post-header {
    margin-bottom: 0.4rem !important;
    padding-bottom: 0 !important;
  }
</style>
