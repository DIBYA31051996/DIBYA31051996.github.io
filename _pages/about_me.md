---
layout: page
title: About Me
permalink: /about-me/
nav: true
nav_order: 2
---

<style>
  .post-header .post-title,
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }
</style>

<div class="about-shell">
  <section class="about-frame">
    <aside class="about-sidebar">
      <div class="about-pill"><span class="about-pill-icon">◉</span> Home • About Me</div>

      <article class="about-profile-card">
        <h2>Dibya Kirti Mishra</h2>
        <p class="about-role">Solar Physicist</p>
        <p class="about-location">ARIES, Nainital, Uttarakhand, India</p>
      </article>

      <div class="about-nav">
        <a class="about-nav-btn active" href="#overview" data-target="overview"><span class="about-nav-icon">◈</span>Overview</a>
        <a class="about-nav-btn" href="#journey" data-target="journey"><span class="about-nav-icon">◈</span>Journey</a>
        <div class="about-nav-btn"><span class="about-nav-icon">◈</span>Research Style</div>
        <div class="about-nav-btn"><span class="about-nav-icon">◈</span>Experience</div>
        <div class="about-nav-btn"><span class="about-nav-icon">◈</span>Skills</div>
        <div class="about-nav-btn"><span class="about-nav-icon">◈</span>Connect</div>
      </div>

      <article class="about-meta-card">
        <div class="about-meta-row">
          <span>Focus</span>
          <strong>Solar cycle, polar fields, ML-ready archival solar datasets</strong>
        </div>
        <div class="about-meta-row">
          <span>Base</span>
          <strong>Nainital, India</strong>
        </div>
        <div class="about-meta-row">
          <span>Next</span>
          <strong>Project pages, software archive, and more writing around research</strong>
        </div>
      </article>
    </aside>

    <section class="about-content">
      <div class="about-heading">
        <h1>About Me</h1>
        <p>This page is the narrative center of the site: who I am, how I got here, how I work, and how the rest of the site fits together.</p>
      </div>

      <section class="about-panel active" data-panel="overview">
        <div class="about-copy">
          <h3>Overview</h3>
          <p>A quick introduction to my scientific profile</p>
        </div>

        <div class="about-card-grid">
          <article class="about-detail-card">
            <h4>What I work on</h4>
            <p>
              I work on solar magnetic-field evolution across multiple cycles, combining observations, long-baseline
              reconstructions, and data-centered methods to better understand long-term solar variability.
            </p>
            <ul>
              <li>Solar cycle variability</li>
              <li>Polar fields and magnetic diagnostics</li>
              <li>ML-ready archival datasets</li>
            </ul>
          </article>

          <article class="about-detail-card">
            <h4>What this site is for</h4>
            <p>
              I want this site to serve as both a research profile and a growing archive: publications, repositories,
              future articles, and eventually topic-specific pages.
            </p>
            <p class="about-note">
              The structure is intentionally modular so more pages can be added without redesigning everything.
            </p>
          </article>
        </div>

        <article class="about-cta-card">
          <h4>Start from the strongest entry points</h4>
          <p>
            Research gives the map, publications provide the record, and repositories hold the tools and code behind the
            work.
          </p>
          <div class="about-actions">
            <a class="about-action-primary" href="{{ '/projects/' | relative_url }}">Open Research</a>
            <a class="about-action-secondary" href="{{ '/publications/' | relative_url }}">Open Publications</a>
            <a class="about-action-secondary" href="{{ '/repositories/' | relative_url }}">Open Repositories</a>
          </div>
        </article>
      </section>

      <section class="about-panel" data-panel="journey" hidden>
        <div class="about-copy">
          <h3>Journey</h3>
          <p>From Puri to solar-physics research</p>
        </div>

        <article class="about-journey-card">
          <div class="about-journey-item">
            <div class="about-journey-dot"></div>
            <div class="about-journey-body">
              <h4>Early years in Puri</h4>
              <small>Puri, Odisha</small>
              <p>
                My journey began in Puri, where curiosity about the natural world slowly grew into a deeper interest in
                physics and the larger questions of astronomy.
              </p>
            </div>
          </div>

          <div class="about-journey-item">
            <div class="about-journey-dot"></div>
            <div class="about-journey-body">
              <h4>Physics training in Delhi</h4>
              <small>University of Delhi, 2013-2016</small>
              <p>
                My undergraduate years gave me the formal grounding in physics that shaped my discipline, problem-solving
                style, and interest in moving toward astrophysics and data-driven scientific work.
              </p>
            </div>
          </div>

          <div class="about-journey-item">
            <div class="about-journey-dot"></div>
            <div class="about-journey-body">
              <h4>Master's pathway into astrophysics</h4>
              <small>Central University of Kerala, 2017-2019</small>
              <p>
                During my master's studies, astrophysics became a clearer direction, and I wanted to work on questions
                connected to the Sun, long-term observations, and physical interpretation.
              </p>
            </div>
          </div>

          <div class="about-journey-item">
            <div class="about-journey-dot"></div>
            <div class="about-journey-body">
              <h4>Research work at ARIES</h4>
              <small>Nainital, from 2020 onward</small>
              <p>
                At ARIES, my work evolved into long-term studies of solar magnetic activity, polar fields, chromospheric
                structures, and machine-learning pipelines built around archival solar data and century-long records.
              </p>
            </div>
          </div>
        </article>
      </section>
    </section>
  </section>
</div>

<script>
document.addEventListener('DOMContentLoaded', function () {
  const tabs = Array.from(document.querySelectorAll('.about-nav a.about-nav-btn[data-target]'));
  const panels = Array.from(document.querySelectorAll('.about-panel'));

  function showPanel(target) {
    tabs.forEach((tab) => {
      tab.classList.toggle('active', tab.dataset.target === target);
    });

    panels.forEach((panel) => {
      const active = panel.dataset.panel === target;
      panel.classList.toggle('active', active);
      panel.hidden = !active;
    });
  }

  tabs.forEach((tab) => {
    tab.addEventListener('click', function (event) {
      event.preventDefault();
      showPanel(tab.dataset.target);
    });
  });
});
</script>
