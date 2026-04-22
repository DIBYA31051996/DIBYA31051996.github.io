---
layout: page
title: Data Analysis
permalink: /data-analysis/
nav: false
---

<style>
  .post-header .post-title,
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }

  .da-shell {
    max-width: 1120px;
    margin: 0 auto;
    padding: 0.3rem 0 1rem;
  }

  .da-panel {
    border-radius: 24px;
    padding: 1.8rem 1.4rem 2rem;
    background:
      radial-gradient(circle at top left, rgba(80, 146, 210, 0.14), transparent 24%),
      radial-gradient(circle at top right, rgba(41, 156, 112, 0.14), transparent 22%),
      linear-gradient(180deg, rgba(13, 20, 38, 0.96), rgba(8, 14, 28, 0.99));
    box-shadow:
      0 20px 44px rgba(0, 0, 0, 0.2),
      inset 0 1px 0 rgba(255, 255, 255, 0.08);
  }

  .da-section + .da-section {
    margin-top: 2.2rem;
  }

  .da-title {
    margin: 0;
    text-align: center;
    font-size: clamp(1.8rem, 3.2vw, 2.5rem);
    font-weight: 800;
    color: #f4f6fb;
    position: relative;
    display: inline-block;
    left: 50%;
    transform: translateX(-50%);
    padding: 0 0.35rem 0.45rem;
    text-shadow: 0 6px 22px rgba(77, 173, 255, 0.24);
  }

  .da-title::after {
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

  .da-rule {
    width: 100%;
    height: 3px;
    margin: 1rem 0 1.5rem;
    border-radius: 999px;
    background: linear-gradient(90deg, rgba(111, 157, 180, 0.88), rgba(111, 157, 180, 0.28));
  }

  .da-grid {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    gap: 1rem;
  }

  .da-card {
    display: flex;
    flex-direction: column;
    border: 1px solid rgba(175, 194, 235, 0.16);
    border-radius: 18px;
    overflow: hidden;
    background:
      linear-gradient(180deg, rgba(16, 24, 43, 0.92), rgba(10, 17, 31, 0.96)),
      radial-gradient(circle at top right, rgba(88, 166, 255, 0.12), transparent 40%);
    transition: transform 0.22s ease, box-shadow 0.22s ease, border-color 0.22s ease;
  }

  .da-card:hover {
    transform: translateY(-4px);
    border-color: rgba(118, 196, 255, 0.46);
    box-shadow:
      0 12px 22px rgba(0, 0, 0, 0.16),
      0 0 0 1px rgba(118, 196, 255, 0.14),
      0 0 10px rgba(77, 173, 255, 0.08);
  }

  .da-visual {
    flex: 0 0 150px;
    height: 150px;
    display: grid;
    place-items: center;
    background:
      linear-gradient(180deg, rgba(243, 246, 255, 0.94), rgba(227, 234, 244, 0.94)),
      radial-gradient(circle at top right, rgba(88, 166, 255, 0.14), transparent 42%);
  }

  .da-visual img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    display: block;
    padding: 1rem;
  }

  .da-body {
    flex: 1 1 auto;
    display: flex;
    flex-direction: column;
    padding: 0.9rem;
  }

  .da-body h3 {
    margin: 0 0 0.4rem;
    font-size: 1rem;
    line-height: 1.35;
    font-weight: 800;
    min-height: 2.8rem;
  }

  .da-body h3 a {
    color: #b8e1ff;
    text-decoration: none;
  }

  .da-body h3 a:hover {
    color: #ffffff;
    text-decoration: underline;
  }

  .da-body p {
    margin: 0;
    color: #d4deef;
    line-height: 1.55;
    font-size: 0.93rem;
    min-height: 5.2rem;
  }

  @media (max-width: 980px) {
    .da-grid {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }

  @media (max-width: 640px) {
    .da-panel {
      padding: 1.35rem 1rem 1.45rem;
    }

    .da-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="da-shell">
  <div class="da-panel">
    <section class="da-section">
      <h1 class="da-title">Data Analysis</h1>
      <div class="da-rule"></div>
      <div class="da-grid">
        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/space-based/soho.jpg' | relative_url }}" alt="STIX Data Center"></div>
          <div class="da-body">
            <h3>STIX Data Center</h3>
            <p>Access point for Spectrometer/Telescope for Imaging X-rays products, flare records, and quick-look analysis material.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/space-based/stereo-wiki.jpg' | relative_url }}" alt="SpaceML"></div>
          <div class="da-body">
            <h3>SpaceML</h3>
            <p>Machine-learning oriented tooling and examples for space-science datasets, event detection, and scalable experimentation.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/long-term/solar-dynamo-user.jpg' | relative_url }}" alt="SERPENTINE Tools"></div>
          <div class="da-body">
            <h3>SERPENTINE Tools</h3>
            <p>Analysis support tools for energetic-particle connectivity, propagation context, and heliospheric event interpretation.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/long-term/resource-monitor.svg' | relative_url }}" alt="CROCS"></div>
          <div class="da-body">
            <h3>CROCS</h3>
            <p>Compact research utilities for catalog handling, comparative diagnostics, and solar-event context studies.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/ground-based/ecallisto.png' | relative_url }}" alt="Radio Monitoring"></div>
          <div class="da-body">
            <h3>Radio Monitoring</h3>
            <p>Radio burst tracking resources and quick-look monitoring tools for dynamic solar activity and event verification.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/space-based/hinode-wiki.jpg' | relative_url }}" alt="HelioML"></div>
          <div class="da-body">
            <h3>HelioML</h3>
            <p>Machine-learning resources and project tooling focused on heliophysics datasets, classification, and forecasting tasks.</p>
          </div>
        </article>
      </div>
    </section>
  </div>
</div>
