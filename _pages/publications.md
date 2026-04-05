---
layout: page
permalink: /publications/
title: Publications
nav: true
nav_order: 4
description: Refereed articles, proceedings, software, and datasets.
---

<style>
  .post-header .post-title,
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }
  .post-header {
    margin-bottom: 0.4rem !important;
    padding-bottom: 0 !important;
  }
</style>

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

      <div class="pub-tools">
        <label class="pub-year-filter" for="pub-year-select" id="pub-year-wrap">
          <span>Year</span>
          <select id="pub-year-select">
            <option value="all">All Years</option>
          </select>
        </label>
        <div class="pub-items-count" id="pub-items-count">0 Items</div>
      </div>
    </div>

    <div class="pub-list" data-section="articles">
      {% bibliography --query @article %}
    </div>

    <div class="pub-list" data-section="proceedings" hidden>
      {% bibliography --query @inproceedings %}
    </div>

    <div class="pub-list" data-section="software" hidden>
      <ul class="bibliography">
        <li data-year="2025">
          <div class="title">SCOOBI</div>
          <div class="author">Dibya Kirti Mishra</div>
          <p class="pub-desc">Solar feature tracking and analysis software for bipolar magnetic regions.</p>
          <div class="periodical-row">
            <div class="periodical"><span class="periodical-copy">Zenodo software record • Python • Solar magnetic regions • Tracking</span></div>
            <div class="pub-date-badge">2025 Jun</div>
          </div>
          <div class="links">
            <a href="https://github.com/DIBYA31051996/scoobi" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> Repo</a>
            <a href="https://github.com/DIBYA31051996/scoobi#readme" target="_blank" rel="noopener"><i class="fa-solid fa-book"></i> Docs</a>
            <a href="https://github.com/DIBYA31051996/scoobi/releases" target="_blank" rel="noopener"><i class="fa-solid fa-arrow-up-right-from-square"></i> Link</a>
          </div>
        </li>
      </ul>
    </div>

    <div class="pub-list" data-section="data" hidden>
      <ul class="bibliography">
        <li data-year="2025">
          <div class="title">PNI Data</div>
          <div class="author">Dibya Kirti Mishra</div>
          <p class="pub-desc">Polar Network Index (PNI) dataset archived on Zenodo for long-baseline solar activity studies.</p>
          <div class="periodical-row">
            <div class="periodical"><span class="periodical-copy">Zenodo dataset record • PNI • Polar fields • Data</span></div>
            <div class="pub-date-badge">2025 Sep</div>
          </div>
          <div class="links">
            <a href="https://zenodo.org/search?q=PNI" target="_blank" rel="noopener"><i class="fa-solid fa-database"></i> Link</a>
          </div>
        </li>
      </ul>
    </div>
  </section>
</div>

<script>
document.addEventListener('DOMContentLoaded', function () {
  document.documentElement.classList.add('js-reveal');

  const navButtons = Array.from(document.querySelectorAll('.pub-nav-btn'));
  const sections = Array.from(document.querySelectorAll('.pub-list[data-section]'));
  const yearSelect = document.getElementById('pub-year-select');
  const yearWrap = document.getElementById('pub-year-wrap');
  const itemsCount = document.getElementById('pub-items-count');
  const sectionTitle = document.getElementById('pub-section-title');
  const sectionSubtitle = document.getElementById('pub-section-subtitle');

  const sectionMeta = {
    articles: { title: 'Refereed Articles', subtitle: 'Journal articles and preprints', yearFilter: true },
    proceedings: { title: 'Proceedings', subtitle: 'Conference and symposium papers', yearFilter: true },
    software: { title: 'Published Software', subtitle: 'Reusable software and code releases', yearFilter: true },
    data: { title: 'Published Data', subtitle: 'Datasets, catalogs, and archives', yearFilter: true }
  };

  function getVisibleSection() {
    return sections.find((s) => !s.hidden);
  }

  function initScrollReveal(scope = document) {
  const cards = Array.from(scope.querySelectorAll('.pub-list:not([hidden]) .bibliography li'));
  if (!cards.length) return;

  cards.forEach((card) => {
    card.classList.remove('reveal-in');
    card.classList.add('reveal-pending');
  });

  const io = new IntersectionObserver((entries, obs) => {
    entries.forEach((entry) => {
      if (!entry.isIntersecting) return;
      const el = entry.target;
      const delay = Number(el.dataset.revealDelay || 0);
      setTimeout(() => {
        el.classList.remove('reveal-pending');
        el.classList.add('reveal-in');
      }, delay);
      obs.unobserve(el);
    });
  }, {
    threshold: 0.12,
    rootMargin: "0px 0px -8% 0px"
  });

  cards.forEach((card, i) => {
    card.dataset.revealDelay = (i * 100).toString(); // one-by-one
    io.observe(card);
  });
}


  
  function collectYears(section) {
    const cardYears = Array.from(section.querySelectorAll('.bibliography li')).map((li) => {
      const attrYear = li.dataset.year;
      if (attrYear) return attrYear;
      const badge = li.querySelector('.pub-date-badge');
      const text = badge ? badge.textContent : li.textContent;
      return (text.match(/\b(19|20)\d{2}\b/) || [])[0];
    }).filter(Boolean);

    if (cardYears.length) {
      return [...new Set(cardYears)].sort((a, b) => Number(b) - Number(a));
    }

    let years = Array.from(section.querySelectorAll('h2.year, h2, h3'))
      .map((el) => (el.textContent.match(/\b(19|20)\d{2}\b/) || [])[0])
      .filter(Boolean);

    if (!years.length) {
      const txt = section.textContent || '';
      years = txt.match(/\b(19|20)\d{2}\b/g) || [];
    }

    return [...new Set(years)].sort((a, b) => Number(b) - Number(a));
  }

  function fillYearOptions() {
    const section = getVisibleSection();
    const years = collectYears(section);
    const prev = yearSelect.value || 'all';

    yearSelect.innerHTML = '<option value="all">All Years</option>';
    years.forEach((year) => {
      const opt = document.createElement('option');
      opt.value = year;
      opt.textContent = year;
      yearSelect.appendChild(opt);
    });
    yearSelect.value = years.includes(prev) ? prev : 'all';
  }

  function applyYearFilter() {
    const section = getVisibleSection();
    const selected = yearSelect.value;
    const cards = Array.from(section.querySelectorAll('.bibliography li'));

    if (cards.length) {
      cards.forEach((li) => {
        const attrYear = li.dataset.year;
        const badge = li.querySelector('.pub-date-badge');
        const text = badge ? badge.textContent : li.textContent;
        const y = attrYear || (text.match(/\b(19|20)\d{2}\b/) || [])[0];
        const show = selected === 'all' || selected === y;
        li.style.display = show ? '' : 'none';
      });
      updateItemsCount();
      return;
    }

    const yearHeaders = Array.from(section.querySelectorAll('h2.year, h2, h3'));

    yearHeaders.forEach((header) => {
      const y = (header.textContent.match(/\b(19|20)\d{2}\b/) || [])[0];
      const list = header.nextElementSibling;
      if (!y || !list) return;

      const show = selected === 'all' || selected === y;
      header.style.display = show ? '' : 'none';
      list.style.display = show ? '' : 'none';
    });

    updateItemsCount();
  }

  function updateItemsCount() {
    const section = getVisibleSection();
    const visibleCards = Array.from(section.querySelectorAll('.bibliography li')).filter((li) => li.offsetParent !== null);
    const n = visibleCards.length;
    itemsCount.textContent = `${n} ${n === 1 ? 'Item' : 'Items'}`;
  }

  function highlightAuthorName() {
    document.querySelectorAll('.pub-list .bibliography li .author').forEach((el) => {
      let html = el.innerHTML;
      html = html.replace(/<span class="me-highlight">(.*?)<\/span>/g, '$1');
      html = html.replace(/Dibya Kirti Mishra/g, '<span class="me-highlight">Dibya Kirti Mishra</span>');
      el.innerHTML = html;
    });
  }

  function makeTitlesClickable() {
    document.querySelectorAll('.pub-list .bibliography li').forEach((li) => {
      const titleEl = li.querySelector('.title');
      if (!titleEl || titleEl.querySelector('a')) return;

      let href = null;
      const links = Array.from(li.querySelectorAll('.links a'));
      if (links.length) {
        const pick =
          links.find(a => /doi/i.test(a.textContent)) ||
          links.find(a => /ads/i.test(a.textContent)) ||
          links.find(a => /arxiv/i.test(a.textContent)) ||
          links[0];
        href = pick?.getAttribute('href') || null;
      }

      if (!href) {
        const txt = li.textContent || '';
        const m = txt.match(/10\.\d{4,9}\/[-._;()/:A-Z0-9]+/i);
        if (m) href = `https://doi.org/${m[0]}`;
      }

      if (!href) return;
      const titleText = titleEl.textContent.trim();
      titleEl.innerHTML = `<a class="pub-title-link" href="${href}" target="_blank" rel="noopener">${titleText}</a>`;
    });
  }

  function initMoreAuthorsToggle(scope = document) {
    scope.querySelectorAll('.more-authors').forEach((el) => {
      if (el.dataset.bound === '1') return;
      el.dataset.bound = '1';

      const toggle = () => {
        const collapsed = el.dataset.collapsed || '';
        const expanded = el.dataset.expanded || '';
        const isCollapsed = (el.dataset.state || 'collapsed') === 'collapsed';
        el.textContent = isCollapsed ? expanded : collapsed;
        el.dataset.state = isCollapsed ? 'expanded' : 'collapsed';
      };

      el.addEventListener('click', toggle);
      el.addEventListener('keydown', (e) => {
        if (e.key === 'Enter' || e.key === ' ') {
          e.preventDefault();
          toggle();
        }
      });
    });
  }

  function revealVisibleCardsOneByOne() {
    const visibleSection = getVisibleSection();
    if (!visibleSection) return;

    const cards = Array.from(visibleSection.querySelectorAll('.bibliography li'));
    cards.forEach((card, i) => {
      card.classList.remove('reveal-in');
      card.style.opacity = '0';
      card.style.transform = 'translateY(22px)';
      card.style.filter = 'blur(2px)';
      setTimeout(() => {
        card.classList.add('reveal-in');
        card.style.opacity = '';
        card.style.transform = '';
        card.style.filter = '';
      }, i * 120);
    });
  }

  function runEnhancements() {
    highlightAuthorName();
    makeTitlesClickable();
    initMoreAuthorsToggle(getVisibleSection());
    initScrollReveal(getVisibleSection());
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

    if (sectionMeta[target].yearFilter) {
      yearWrap.style.display = '';
      fillYearOptions();
      applyYearFilter();
    } else {
      yearWrap.style.display = 'none';
      updateItemsCount();
    }

    runEnhancements();
  }

  navButtons.forEach((btn) => btn.addEventListener('click', () => switchSection(btn.dataset.target)));
  yearSelect.addEventListener('change', () => {
    applyYearFilter();
    revealVisibleCardsOneByOne();
  });

  switchSection('articles');
});
</script>
