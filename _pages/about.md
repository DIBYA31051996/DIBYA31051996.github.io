---
layout: page
title: Home
permalink: /
nav: true
nav_order: 1
---

<style>
  .post-title,
  .post-description {
    display: none;
  }
</style>

<div class="home-shell">
  <section class="home-hero">
    <div class="home-main home-card">
      <div class="home-pill"><span class="dot"></span> Solar Physicist</div>

      <div class="home-title-wrap">
        <h1 class="home-title">
          <span class="home-title-typed">Hi, I am <span class="home-title-typed-gradient">Dibya Kirti Mishra</span></span>
        </h1>
      </div>

      <p class="home-lead">
        I study solar magnetic fields, solar cycle variability, and data-rich heliophysics workflows that improve
        long-baseline analysis and solar dynamo model understanding.
      </p>

      <div class="home-actions">
        <a class="btn btn-primary" href="{{ '/projects/' | relative_url }}">Explore Research</a>
        <a class="btn btn-ghost" href="{{ '/about-me/' | relative_url }}">About Me</a>
        <a class="btn btn-ghost" href="{{ '/publications/' | relative_url }}">Browse Publications</a>
      </div>

      <div class="home-stats">
        <div class="stat-card">
          <strong>5</strong>
          <span>Refereed publications</span>
        </div>
        <div class="stat-card">
          <strong>6</strong>
          <span>Research themes</span>
        </div>
        <div class="stat-card">
          <strong>ARIES</strong>
          <span>Long term variability in the sun</span>
        </div>
      </div>

      <article class="home-story">
        <h3>My Journey: From Odisha to Solar Physics</h3>
        <p>
          I am currently working on long-term solar activity, chromospheric and sunspot analysis, and machine-learning
          ready data products for heliophysics research. My work connects observational solar records with physically
          grounded modeling so we can better understand the structure and evolution of solar cycles.
        </p>
        <p>
          My research interests include solar cycle variability, surface and advective flux transport, data curation for
          forecasting workflows, and publication-ready scientific communication. This website brings those pieces
          together into a cleaner research home.
        </p>
      </article>

      <article class="home-publication-card">
        <div class="section-kicker">Latest publication</div>
        <h3>Machine Learning-based Identification of the Solar Disk and Plages in Kodaikanal Solar Observatory Historical Suncharts</h3>
        <p>
          Published in <em>The Astrophysical Journal Supplement Series</em> in March 2026, this work focuses on
          machine-learning driven identification of solar-disk structure and plages from historical Kodaikanal
          suncharts.
        </p>
        <a href="{{ '/publications/' | relative_url }}">View publication archive</a>
      </article>

      <div class="home-mini-links">
        <a class="mini-link" href="{{ '/repositories/' | relative_url }}">Code / repositories</a>
        <a class="mini-link" href="{{ '/cv/' | relative_url }}">CV / resume</a>
      </div>
    </div>

    <aside class="home-sidebar">
      <div class="profile-panel home-card">
        <img src="{{ '/assets/img/RIP07945.png' | relative_url }}" alt="Portrait of Dibya Kirti Mishra" />
        <div class="profile-panel-body">
          <p class="profile-label">Dibya Kirti Mishra</p>
          <h2>Solar Researcher</h2>
          <p class="profile-meta">Aryabhatta Research Institute of Observational Sciences (ARIES), Nainital, India</p>
          <div class="profile-tags">
            <a href="{{ '/about-me/' | relative_url }}">Connect</a>
            <a href="{{ '/projects/' | relative_url }}">Research</a>
            <a href="https://github.com/DIBYA31051996" target="_blank" rel="noopener">Github</a>
          </div>
          <a class="sidebar-button" href="{{ '/publications/' | relative_url }}">Publications</a>
        </div>
      </div>

      <div class="updates-panel home-card">
        <h3>Recent highlights</h3>
        <div class="update-item">
          <small>Mar 2026</small>
          <strong>ApJS publication on machine-learning based plage identification from historical solar suncharts.</strong>
          <p>Historical Kodaikanal observations are turned into cleaner, analysis-ready solar activity products.</p>
        </div>
        <div class="update-item">
          <small>Apr 2025</small>
          <strong>Polar Network Index study published as a proxy for the historical polar magnetic field.</strong>
          <p>This work strengthens long-baseline magnetic-field reconstruction using Ca II K observations.</p>
        </div>
        <div class="update-item">
          <small>Jan 2024</small>
          <strong>Century-long chromospheric differential rotation analysis from Kodaikanal Ca II K data.</strong>
          <p>A long-timescale perspective on solar chromospheric rotation and its observational evolution.</p>
        </div>
      </div>
    </aside>
  </section>

  <section class="home-section">
    <div class="section-heading">
      <div>
        <div class="section-kicker">Research themes</div>
        <h2>Active areas</h2>
      </div>
    </div>

    <div class="card-grid card-grid-3">
      <article class="info-card home-card">
        <h3>Solar cycle variability</h3>
        <p>Long-baseline evolution, reversals, asymmetry, and cycle-to-cycle structure across multiple observables.</p>
        <a href="{{ '/projects/' | relative_url }}">Open theme</a>
      </article>
      <article class="info-card home-card">
        <h3>SFT / AFT modeling</h3>
        <p>Flux-transport based magnetic evolution with observational constraints and data-assimilation workflows.</p>
        <a href="{{ '/projects/' | relative_url }}">Open theme</a>
      </article>
      <article class="info-card home-card">
        <h3>ML-ready solar data</h3>
        <p>Calibration, detection, curation, and forecasting-oriented products designed for reuse and analysis.</p>
        <a href="{{ '/projects/' | relative_url }}">Open theme</a>
      </article>
    </div>
  </section>

  <section class="home-section">
    <div class="section-heading">
      <div>
        <div class="section-kicker">Site roadmap</div>
        <h2>What lives here</h2>
      </div>
    </div>

    <div class="card-grid card-grid-3">
      <article class="info-card home-card accent-card">
        <div class="card-badge">About</div>
        <h3>About, research, publications, and CV</h3>
        <p>The core sections are organized so visitors can quickly understand your background and current work.</p>
      </article>
      <article class="info-card home-card accent-card">
        <div class="card-badge">Projects</div>
        <h3>Project pages and future data notes</h3>
        <p>Dedicated project summaries can grow into dataset pages, reproducible workflows, and visual explainers.</p>
      </article>
      <article class="info-card home-card accent-card">
        <div class="card-badge">Publications</div>
        <h3>Publication and highlight snapshots</h3>
        <p>Recent outputs, selected papers, and short summaries can anchor the homepage without overwhelming it.</p>
      </article>
    </div>
  </section>

  <section class="home-cta home-card">
    <div>
      <div class="section-kicker">Latest connect</div>
      <h2>Let us connect</h2>
      <p>
        For collaborations, solar-physics discussions, and data-product ideas, use the publication archive and profile
        pages as your starting point.
      </p>
    </div>
    <div class="cta-actions">
      <a class="btn btn-soft" href="{{ '/about-me/' | relative_url }}">Open Profile</a>
      <a class="btn btn-soft" href="{{ '/projects/' | relative_url }}">Open Research</a>
      <a class="btn btn-primary" href="{{ '/publications/' | relative_url }}">View Publications</a>
    </div>
  </section>
</div>
