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
    color: #7f0b13;
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

  .dt-card-link {
    display: block;
    color: inherit;
    text-decoration: none;
  }

  .dt-card-link:hover {
    color: inherit;
    text-decoration: none;
  }

  .dt-card-link:hover .dt-visual {
    transform: translateY(-3px);
    box-shadow:
      0 16px 34px rgba(0, 0, 0, 0.18),
      inset 0 1px 0 rgba(255, 255, 255, 0.72);
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
    transition: transform 0.2s ease, box-shadow 0.2s ease;
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
    color: #9d1419;
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

  @media (max-width: 980px) {
    .dt-grid {
      grid-template-columns: repeat(2, minmax(0, 1fr));
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
          <a class="dt-card-link" href="{{ '/ground-based/' | relative_url }}">
            <div class="dt-visual"><div class="dt-icon">📡</div></div>
            <h3>Ground Based</h3>
            <p><strong>Open page:</strong> solar telescopes, microwave, radio</p>
          </a>
        </article>

        <article class="dt-card">
          <a class="dt-card-link" href="{{ '/long-term/' | relative_url }}">
            <div class="dt-visual"><div class="dt-icon">⏳</div></div>
            <h3>Long-Term</h3>
            <p><strong>Open page:</strong> monitoring, forecast, archives</p>
          </a>
        </article>

        <article class="dt-card">
          <a class="dt-card-link" href="{{ '/space-based/' | relative_url }}">
            <div class="dt-visual"><div class="dt-icon">🚀</div></div>
            <h3>Space Based</h3>
            <p><strong>Open page:</strong> probe, orbiter, observatories</p>
          </a>
        </article>

        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon">🌊</div></div>
          <h3>Simulations</h3>
          <p><strong>E.g.</strong> Bifrost, MURaM</p>
        </article>
      </div>
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
