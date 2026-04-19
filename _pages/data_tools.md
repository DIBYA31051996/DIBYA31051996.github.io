---
layout: page
title: Data and Tools
permalink: /data-tools/
nav: true
nav_order: 4
---

<style>
  .post-header .post-title,
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }

  .dt-shell {
    max-width: 1120px;
    margin: 0 auto;
    padding: 0.5rem 0 1rem;
  }

  .dt-panel {
    background:
      radial-gradient(circle at top left, rgba(73, 143, 204, 0.2), transparent 26%),
      radial-gradient(circle at top right, rgba(39, 148, 113, 0.18), transparent 24%),
      linear-gradient(180deg, rgba(13, 20, 38, 0.96), rgba(8, 14, 28, 0.99));
    border-radius: 24px;
    padding: 2.1rem 2rem 2.3rem;
    box-shadow:
      0 18px 44px rgba(0, 0, 0, 0.18),
      0 1px 0 rgba(255, 255, 255, 0.08) inset;
  }

  .dt-section + .dt-section {
    margin-top: 2.3rem;
  }

  .dt-title {
    margin: 0;
    text-align: center;
    font-size: clamp(2rem, 4vw, 3rem);
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: #7f0b13;
    text-decoration: underline;
    text-decoration-thickness: 3px;
    text-underline-offset: 7px;
    font-weight: 800;
  }

  .dt-title.tools {
    color: #f7f8fb;
  }

  .dt-rule {
    width: 100%;
    height: 3px;
    margin: 1.8rem 0 1.6rem;
    border-radius: 999px;
    background: linear-gradient(90deg, rgba(111, 157, 180, 0.88), rgba(111, 157, 180, 0.3));
  }

  .dt-grid {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    gap: 1.3rem;
  }

  .dt-card {
    text-align: center;
    color: #f4f6fb;
  }

  .dt-visual {
    aspect-ratio: 1 / 1;
    border-radius: 24px;
    display: grid;
    place-items: center;
    margin-bottom: 1rem;
    overflow: hidden;
    background:
      linear-gradient(180deg, rgba(243, 246, 255, 0.94), rgba(227, 234, 244, 0.94)),
      radial-gradient(circle at top right, rgba(88, 166, 255, 0.14), transparent 42%);
    box-shadow:
      0 12px 30px rgba(0, 0, 0, 0.12),
      inset 0 1px 0 rgba(255, 255, 255, 0.68);
  }

  .dt-icon {
    font-size: clamp(4rem, 7vw, 6rem);
    line-height: 1;
    filter: saturate(1.05);
  }

  .dt-card h3 {
    margin: 0 0 0.55rem;
    font-size: 1.45rem;
    line-height: 1.15;
    text-transform: uppercase;
    color: #9d1419;
    font-weight: 800;
  }

  .dt-tools .dt-card h3 {
    color: #f5f7fb;
  }

  .dt-card p {
    margin: 0;
    font-size: 1.02rem;
    color: #d9e2f3;
    line-height: 1.55;
  }

  .dt-card p strong {
    color: #ffffff;
    font-weight: 700;
  }

  .dt-feature {
    margin-top: 1.7rem;
    border: 1px solid rgba(169, 191, 227, 0.18);
    border-radius: 24px;
    padding: 1.35rem;
    background:
      linear-gradient(180deg, rgba(17, 25, 46, 0.88), rgba(11, 18, 35, 0.94)),
      radial-gradient(circle at top right, rgba(77, 129, 218, 0.12), transparent 38%);
    box-shadow:
      0 18px 36px rgba(0, 0, 0, 0.18),
      inset 0 1px 0 rgba(255, 255, 255, 0.05);
  }

  .dt-feature h3 {
    margin: 0 0 0.35rem;
    color: #f7f9fd;
    font-size: 1.65rem;
    font-weight: 800;
  }

  .dt-feature-intro {
    margin: 0 0 1rem;
    color: #d4def0;
    line-height: 1.65;
  }

  .dt-feature-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 1rem;
  }

  .dt-feature-block {
    border: 1px solid rgba(175, 194, 235, 0.14);
    border-radius: 18px;
    padding: 1rem;
    background: rgba(255, 255, 255, 0.04);
  }

  .dt-feature-block h4 {
    margin: 0 0 0.55rem;
    color: #f7f9fd;
    font-size: 1.15rem;
    font-weight: 800;
  }

  .dt-feature-block p {
    margin: 0;
    color: #d7e0f2;
    line-height: 1.62;
  }

  .dt-feature-block p + p {
    margin-top: 0.7rem;
  }

  @media (max-width: 980px) {
    .dt-grid {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }

    .dt-feature-grid {
      grid-template-columns: 1fr;
    }
  }

  @media (max-width: 640px) {
    .dt-panel {
      padding: 1.4rem 1rem 1.5rem;
    }

    .dt-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="dt-shell">
  <div class="dt-panel">
    <section class="dt-section dt-data">
      <h1 class="dt-title">Data</h1>
      <div class="dt-rule"></div>

      <div class="dt-grid">
        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon">📡</div></div>
          <h3>Ground Based</h3>
          <p><strong>E.g.</strong> KoSO, SST, GONG</p>
        </article>

        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon">⏳</div></div>
          <h3>Long-Term</h3>
          <p><strong>E.g.</strong> KoSO, MWO, RGO</p>
        </article>

        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon">🚀</div></div>
          <h3>Space Based</h3>
          <p><strong>E.g.</strong> SoHO, SDO, Solar Orbiter</p>
        </article>

        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon">🌊</div></div>
          <h3>Simulations</h3>
          <p><strong>E.g.</strong> Bifrost, MURaM</p>
        </article>
      </div>

      <article class="dt-feature">
        <h3>Ground Based Instruments</h3>
        <p class="dt-feature-intro">
          Ground-based observations span high-resolution solar telescopes, radio observatories, and synoptic networks
          that track solar structure, magnetism, and activity across multiple wavelengths and timescales.
        </p>

        <div class="dt-feature-grid">
          <section class="dt-feature-block">
            <h4>Solar Telescopes</h4>
            <p>
              Leading ground-based observations include the Dunn Solar Telescope, DKIST, the Swedish 1-m Solar Telescope
              (SST), and the upcoming European Solar Telescope (EST).
            </p>
            <p>
              These instruments use adaptive optics and high-resolution spectrographs to capture fine details of the
              solar surface, magnetic fields, and evolving sunspot regions.
            </p>
          </section>

          <section class="dt-feature-block">
            <h4>Radio Observatories</h4>
            <p>
              Facilities such as EOVSA, the Nancay Radioheliograph, the Nobeyama Radioheliograph, and the Gauribidanur
              Radioheliograph observe the Sun in radio wavelengths.
            </p>
            <p>
              They help track radio emission associated with flares, coronal mass ejections, and solar energetic
              particle events.
            </p>
          </section>

          <section class="dt-feature-block">
            <h4>Synoptic Solar Telescopes</h4>
            <p>
              Long-running synoptic instruments such as GONG support the study of solar oscillations, interior
              structure, and large-scale dynamical evolution.
            </p>
            <p>
              These datasets are especially useful for long-baseline solar-cycle analysis and context building across
              multiple observing programs.
            </p>
          </section>
        </div>
      </article>
    </section>

    <section class="dt-section dt-tools">
      <div class="dt-rule"></div>
      <h2 class="dt-title tools">Tools</h2>
      <div class="dt-rule"></div>

      <div class="dt-grid">
        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon">📊</div></div>
          <h3>Data Analysis</h3>
          <p><strong>E.g.</strong> Python, IDL, Fortran workflows</p>
        </article>

        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon">📈</div></div>
          <h3>Data Visualization</h3>
          <p><strong>E.g.</strong> Matplotlib, map plots, diagnostics</p>
        </article>

        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon">🤖</div></div>
          <h3>AI &amp; ML</h3>
          <p><strong>E.g.</strong> CNN pipelines, detection models</p>
        </article>

        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon">🧩</div></div>
          <h3>Modeling</h3>
          <p><strong>E.g.</strong> Flux transport and reconstruction tools</p>
        </article>
      </div>
    </section>
  </div>
</div>
