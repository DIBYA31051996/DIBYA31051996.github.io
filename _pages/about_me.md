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
        <div class="about-nav-btn active"><span class="about-nav-icon">◈</span>Overview</div>
        <div class="about-nav-btn"><span class="about-nav-icon">◈</span>Journey</div>
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
  </section>
</div>
