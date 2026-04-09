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
          My research focuses on the long-term evolution of solar magnetic activity and its implications for solar
          dynamo theory and solar cycle prediction. I work extensively with century-long Ca II K and Hα datasets from
          the Kodaikanal Solar Observatory, complemented by observations from Mount Wilson Observatory, PSPT Rome, and
          space-based missions such as the Solar Dynamics Observatory.
        </p>
        <p>
          I specialize in developing automated algorithms (Python/IDL) for feature detection and for constructing
          long-term time series from both historical and modern solar data. My work includes long-term analysis of
          chromospheric differential rotation using KoSO Ca II K data (1904-2007), automated identification of polar
          network bright points to reconstruct historical polar magnetic fields back to 1904, and machine-learning
          (CNN-based) detection of plages in century-long hand-drawn sun charts. I have also contributed to the
          construction of long-term Carrington maps using Ca II K observations, multi-wavelength studies of
          upper-atmospheric differential rotation using SDO/AIA data, and the development of ML-based pipelines for
          automated detection of sunspot groups and tilt angles from KoSO white-light data. Additionally, I am involved
          in efforts to reconstruct pre-1976 magnetograms using Ca II K and Hα data through generative AI approaches.
        </p>
        <p>
          Overall, my expertise lies at the intersection of archival solar observations, automated feature-extraction
          techniques, and machine learning, aimed at improving our understanding of long-term solar variability and
          advancing solar cycle prediction.
        </p>
        <p>
          My journey into solar physics began in Puri, Odisha. I completed my B.Sc. from the University of Delhi and
          my M.Sc. from the Central University of Kerala, where my interest in astrophysics steadily took shape. In
          2020, I joined ARIES, Nainital, where my research evolved into a more quantitative and data-driven
          exploration of the Sun. This platform reflects both my scientific work and the path that led me here, from
          the shores of Puri to the study of solar activity.
        </p>
      </article>

      <article class="home-publication-card">
        <div class="section-kicker publication-kicker">Latest Publication</div>
        <h3><strong>Machine Learning-based Identification of the Solar Disk and Plages in Kodaikanal Solar Observatory Historical Suncharts</strong></h3>
        <p>
          Published in <em>The Astrophysical Journal Supplement Series</em> in March 2026, this work focuses on
          machine-learning driven identification of solar-disk structure and plages from historical Kodaikanal
          suncharts.
        </p>
        <a href="{{ '/publications/' | relative_url }}"><strong>View publication archive</strong></a>
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
          <small>19 Nov 2025</small>
          <strong><a href="https://dst.gov.in/century-long-data-kodaikanal-observatory-reveals-clues-suns-future" target="_blank" rel="noopener">Century-long data of Kodaikanal Observatory reveals clues to Sun's future</a></strong>
          <p>DST coverage of the Kodaikanal solar-data study and its implications for future solar-cycle understanding.</p>
        </div>
        <div class="update-item">
          <small>19 Nov 2025</small>
          <strong><a href="https://www.pib.gov.in/PressReleasePage.aspx?PRID=2191662&reg=3&lang=2" target="_blank" rel="noopener">Century-long data of Kodaikanal Observatory reveals clues to Sun's future</a></strong>
          <p>PIB release highlighting the role of century-long observatory records in understanding the Sun's future behavior.</p>
        </div>
        <div class="update-item">
          <small>19 Nov 2025</small>
          <strong><a href="https://ddnews.gov.in/en/century-old-kodaikanal-observatory-data-offers-new-insights-into-the-suns-magnetic-future/" target="_blank" rel="noopener">Century-old Kodaikanal Observatory data offers new insights into the Sun's magnetic future</a></strong>
          <p>DD News coverage of how long-term Kodaikanal observations refine insight into the Sun's magnetic future.</p>
        </div>
        <div class="update-item">
          <small>20 Jan 2026</small>
          <strong><a href="https://www.swri.org/newsroom/press-releases/using-100-year-old-data-help-predict-future-solar-cycle-activity" target="_blank" rel="noopener">Using 100-year-old data to help predict future solar cycle activity</a></strong>
          <p>Southwest Research Institute summary of how archival solar records improve forecasting of future cycles.</p>
        </div>
        <div class="update-item">
          <small>21 Jan 2026</small>
          <strong><a href="https://spacedaily.com/century-old-solar-records-refine-future-cycle-forecasts-999/" target="_blank" rel="noopener">Century-old solar records refine future cycle forecasts</a></strong>
          <p>SpaceDaily report on how old Ca II K records sharpen solar-cycle forecast constraints.</p>
        </div>
        <div class="update-item">
          <small>06 Mar 2026</small>
          <strong><a href="https://www.universetoday.com/articles/making-new-solar-activity-connections-from-old-data" target="_blank" rel="noopener">Making New Solar Activity Connections From Old Data</a></strong>
          <p>Universe Today feature connecting historical solar observations with new interpretations of solar activity.</p>
        </div>
      </div>
    </aside>
  </section>

  <section class="home-section">
    <div class="meta-strip">
      <article class="meta-card home-card">
        <div class="meta-kicker">Currently Working On</div>
        <p>Solar cycle • Synoptic maps</p>
      </article>
      <article class="meta-card home-card">
        <div class="meta-kicker">Tooling</div>
        <p>Python • HDF5 • Visualization</p>
      </article>
    </div>

    <div class="section-heading">
      <div>
        <h2>Research themes</h2>
      </div>
    </div>

    <div class="card-grid card-grid-2">
      <article class="info-card home-card">
        <h3><strong><span class="theme-icon">◉</span> Solar cycle variability</strong></h3>
        <p>Long-baseline evolution, reversals, asymmetry, and cycle-to-cycle structure across multiple observables.</p>
        <a href="{{ '/projects/' | relative_url }}">Open theme <span aria-hidden="true">↗</span></a>
      </article>
      <article class="info-card home-card">
        <h3><strong><span class="theme-icon">✦</span> ML-ready solar data</strong></h3>
        <p>Calibration, detection, curation, and forecasting-oriented products designed for reuse and analysis.</p>
        <a href="{{ '/projects/' | relative_url }}">Open theme <span aria-hidden="true">↗</span></a>
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
