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
      radial-gradient(circle at 12% 10%, rgba(73, 143, 204, 0.24), transparent 24%),
      radial-gradient(circle at 88% 12%, rgba(39, 148, 113, 0.2), transparent 22%),
      radial-gradient(circle at 50% 100%, rgba(95, 126, 255, 0.14), transparent 28%),
      linear-gradient(180deg, rgba(13, 20, 38, 0.96), rgba(8, 14, 28, 0.99));
    border-radius: 24px;
    padding: 2.1rem 2rem 2.3rem;
    box-shadow:
      0 18px 44px rgba(0, 0, 0, 0.18),
      0 1px 0 rgba(255, 255, 255, 0.08) inset,
      0 0 0 1px rgba(129, 191, 255, 0.08);
  }

  .dt-section + .dt-section {
    margin-top: 2.3rem;
  }

  .dt-title {
    margin: 0;
    text-align: center;
    font-size: clamp(2rem, 4vw, 3rem);
    letter-spacing: 0.04em;
    color: #f4f6fb;
    text-shadow: 0 6px 22px rgba(77, 173, 255, 0.24);
    font-weight: 800;
    position: relative;
    display: inline-block;
    left: 50%;
    transform: translateX(-50%);
    padding: 0 0.35rem 0.45rem;
  }

  .dt-title::before {
    content: "";
    position: absolute;
    top: -0.18rem;
    left: -1rem;
    width: 0.68rem;
    height: 0.68rem;
    border-radius: 999px;
    background: linear-gradient(135deg, #72ddff 0%, #7c8dff 100%);
    box-shadow: 0 0 16px rgba(114, 221, 255, 0.45);
  }

  .dt-title::after {
    content: "";
    position: absolute;
    left: 50%;
    bottom: 0;
    width: min(220px, 70%);
    height: 4px;
    border-radius: 999px;
    transform: translateX(-50%);
    background: linear-gradient(90deg, rgba(93, 157, 255, 0.15), rgba(123, 223, 183, 0.95), rgba(93, 157, 255, 0.15));
    box-shadow: 0 0 18px rgba(123, 223, 183, 0.28);
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

  .dt-data .dt-card:nth-child(1) {
    --dt-accent: #67d9ff;
    --dt-accent-soft: rgba(103, 217, 255, 0.18);
    --dt-badge-bg: rgba(103, 217, 255, 0.12);
  }

  .dt-data .dt-card:nth-child(2) {
    --dt-accent: #77ffc8;
    --dt-accent-soft: rgba(119, 255, 200, 0.18);
    --dt-badge-bg: rgba(119, 255, 200, 0.12);
  }

  .dt-data .dt-card:nth-child(3) {
    --dt-accent: #8da7ff;
    --dt-accent-soft: rgba(141, 167, 255, 0.18);
    --dt-badge-bg: rgba(141, 167, 255, 0.12);
  }

  .dt-data .dt-card:nth-child(4) {
    --dt-accent: #ffbf70;
    --dt-accent-soft: rgba(255, 191, 112, 0.18);
    --dt-badge-bg: rgba(255, 191, 112, 0.12);
  }

  .dt-tools .dt-card:nth-child(1) {
    --dt-accent: #8ae1ff;
    --dt-accent-soft: rgba(138, 225, 255, 0.16);
    --dt-badge-bg: rgba(138, 225, 255, 0.12);
  }

  .dt-tools .dt-card:nth-child(2) {
    --dt-accent: #ff8fb3;
    --dt-accent-soft: rgba(255, 143, 179, 0.14);
    --dt-badge-bg: rgba(255, 143, 179, 0.12);
  }

  .dt-tools .dt-card:nth-child(3) {
    --dt-accent: #b68fff;
    --dt-accent-soft: rgba(182, 143, 255, 0.16);
    --dt-badge-bg: rgba(182, 143, 255, 0.12);
  }

  .dt-tools .dt-card:nth-child(4) {
    --dt-accent: #7fffc0;
    --dt-accent-soft: rgba(127, 255, 192, 0.14);
    --dt-badge-bg: rgba(127, 255, 192, 0.12);
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
      inset 0 1px 0 rgba(255, 255, 255, 0.72),
      0 0 0 1px color-mix(in srgb, var(--dt-accent, #75cfff) 35%, white 10%);
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
    position: relative;
  }

  .dt-visual::after {
    content: "";
    position: absolute;
    inset: 0;
    background:
      linear-gradient(135deg, var(--dt-accent-soft, rgba(114, 221, 255, 0.12)), transparent 38%),
      radial-gradient(circle at 80% 20%, color-mix(in srgb, var(--dt-accent, #7c8dff) 22%, white 10%), transparent 28%);
    pointer-events: none;
  }

  .dt-icon {
    font-size: clamp(1rem, 2vw, 1.2rem);
    line-height: 1.2;
    color: #18324a;
    font-weight: 800;
    letter-spacing: 0.04em;
    text-transform: uppercase;
    padding: 0.9rem 1rem;
    border-radius: 18px;
    background: color-mix(in srgb, var(--dt-badge-bg, rgba(255, 255, 255, 0.48)) 70%, white 28%);
    border: 1px solid color-mix(in srgb, var(--dt-accent, #7cc9ff) 32%, white 18%);
    box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.58);
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
  }

  .dt-icon-mark {
    width: 0.95rem;
    height: 0.95rem;
    border-radius: 999px;
    background: var(--dt-accent, #7cc9ff);
    box-shadow: 0 0 14px color-mix(in srgb, var(--dt-accent, #7cc9ff) 55%, transparent);
  }

  .dt-card h3 {
    margin: 0 0 0.55rem;
    font-size: 1.45rem;
    line-height: 1.15;
    text-transform: none;
    color: #f4f6fb;
    font-weight: 800;
    text-shadow: 0 0 14px rgba(102, 191, 255, 0.08);
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
            <div class="dt-visual"><div class="dt-icon"><span class="dt-icon-mark"></span>Ground</div></div>
            <h3>Ground Based</h3>
            <p><strong>Open page:</strong> solar telescopes, microwave, radio</p>
          </a>
        </article>

        <article class="dt-card">
          <a class="dt-card-link" href="{{ '/long-term/' | relative_url }}">
            <div class="dt-visual"><div class="dt-icon"><span class="dt-icon-mark"></span>Long</div></div>
            <h3>Long-Term</h3>
            <p><strong>Open page:</strong> monitoring, forecast, archives</p>
          </a>
        </article>

        <article class="dt-card">
          <a class="dt-card-link" href="{{ '/space-based/' | relative_url }}">
            <div class="dt-visual"><div class="dt-icon"><span class="dt-icon-mark"></span>Space</div></div>
            <h3>Space Based</h3>
            <p><strong>Open page:</strong> probe, orbiter, observatories</p>
          </a>
        </article>

        <article class="dt-card">
          <a class="dt-card-link" href="https://sdc.uio.no/search/simulations" target="_blank" rel="noopener">
            <div class="dt-visual"><div class="dt-icon"><span class="dt-icon-mark"></span>Sim</div></div>
            <h3>Simulations</h3>
            <p><strong>Open link:</strong> Bifrost, MURaM, archived runs</p>
          </a>
        </article>
      </div>
    </section>

    <section class="dt-section dt-tools">
      <div class="dt-rule"></div>
      <h2 class="dt-title">Tools</h2>
      <div class="dt-rule"></div>

      <div class="dt-grid">
        <article class="dt-card">
          <a class="dt-card-link" href="{{ '/data-analysis/' | relative_url }}">
            <div class="dt-visual"><div class="dt-icon"><span class="dt-icon-mark"></span>Analyze</div></div>
            <h3>Data Analysis</h3>
            <p><strong>Open page:</strong> software, archives, diagnostics</p>
          </a>
        </article>

        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon"><span class="dt-icon-mark"></span>Visual</div></div>
          <h3>Data Visualization</h3>
          <p><strong>E.g.</strong> Matplotlib, map plots, diagnostics</p>
        </article>

        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon"><span class="dt-icon-mark"></span>ML</div></div>
          <h3>AI &amp; ML</h3>
          <p><strong>E.g.</strong> CNN pipelines, detection models</p>
        </article>

        <article class="dt-card">
          <div class="dt-visual"><div class="dt-icon"><span class="dt-icon-mark"></span>Model</div></div>
          <h3>Modeling</h3>
          <p><strong>E.g.</strong> Flux transport and reconstruction tools</p>
        </article>
      </div>
    </section>
  </div>
</div>
