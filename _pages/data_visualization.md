---
layout: page
title: Data Visualization
permalink: /data-visualization/
nav: false
---

<style>
  .post-header .post-title,
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }

  .dv-shell {
    max-width: 1120px;
    margin: 0 auto;
    padding: 0.3rem 0 1rem;
  }

  .dv-panel {
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

  .dv-title {
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

  .dv-title::after {
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

  .dv-rule {
    width: 100%;
    height: 3px;
    margin: 1rem 0 1.5rem;
    border-radius: 999px;
    background: linear-gradient(90deg, rgba(111, 157, 180, 0.88), rgba(111, 157, 180, 0.28));
  }

  .dv-grid {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    gap: 1rem;
  }

  .dv-card {
    display: flex;
    flex-direction: column;
    min-height: 350px;
    border: 1px solid rgba(175, 194, 235, 0.16);
    border-radius: 18px;
    overflow: hidden;
    background:
      linear-gradient(180deg, rgba(16, 24, 43, 0.92), rgba(10, 17, 31, 0.96)),
      radial-gradient(circle at top right, rgba(88, 166, 255, 0.12), transparent 40%);
    transition: transform 0.22s ease, box-shadow 0.22s ease, border-color 0.22s ease;
  }

  .dv-card:hover {
    transform: translateY(-4px);
    border-color: rgba(118, 196, 255, 0.46);
    box-shadow:
      0 12px 22px rgba(0, 0, 0, 0.16),
      0 0 0 1px rgba(118, 196, 255, 0.14),
      0 0 10px rgba(77, 173, 255, 0.08);
  }

  .dv-visual {
    flex: 0 0 170px;
    height: 170px;
    position: relative;
    overflow: hidden;
    background:
      linear-gradient(180deg, rgba(243, 246, 255, 0.94), rgba(227, 234, 244, 0.94)),
      radial-gradient(circle at top right, rgba(88, 166, 255, 0.14), transparent 42%);
  }

  .dv-visual::after {
    content: "";
    position: absolute;
    inset: 0;
    background:
      linear-gradient(135deg, rgba(88, 166, 255, 0.16), transparent 42%),
      radial-gradient(circle at 82% 20%, rgba(105, 255, 207, 0.16), transparent 28%);
    pointer-events: none;
  }

  .dv-visual img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }

  .dv-body {
    flex: 1 1 auto;
    display: flex;
    flex-direction: column;
    padding: 0.95rem;
  }

  .dv-body h3 {
    margin: 0 0 0.4rem;
    min-height: 2.9rem;
    font-size: 1rem;
    line-height: 1.35;
    font-weight: 800;
  }

  .dv-body h3 a {
    color: #b8e1ff;
    text-decoration: none;
  }

  .dv-body h3 a:hover {
    color: #ffffff;
    text-decoration: underline;
  }

  .dv-body p {
    margin: 0;
    color: #d4deef;
    line-height: 1.55;
    font-size: 0.93rem;
    min-height: 6.45rem;
  }

  @media (max-width: 980px) {
    .dv-grid {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }

  @media (max-width: 640px) {
    .dv-panel {
      padding: 1.35rem 1rem 1.45rem;
    }

    .dv-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="dv-shell">
  <div class="dv-panel">
    <section class="dv-section">
      <h1 class="dv-title">Data Visualization</h1>
      <div class="dv-rule"></div>
      <div class="dv-grid">
        <article class="dv-card">
          <div class="dv-visual"><img src="{{ '/assets/img/long-term/solarmonitor-live.png' | relative_url }}" alt="JHelioviewer"></div>
          <div class="dv-body">
            <h3><a href="https://www.jhelioviewer.org/" target="_blank" rel="noopener">JHelioviewer</a></h3>
            <p>JPEG 2000 based solar image browser for quick event exploration, timeline playback, and layered heliophysics context.</p>
          </div>
        </article>

        <article class="dv-card">
          <div class="dv-visual"><img src="{{ '/assets/img/long-term/solar-activity-user.jpg' | relative_url }}" alt="VisIt"></div>
          <div class="dv-body">
            <h3><a href="https://visit-dav.github.io/visit-website/" target="_blank" rel="noopener">VisIt</a></h3>
            <p>Open-source interactive visualization environment for large multidimensional datasets, animation, and exploratory analysis.</p>
          </div>
        </article>

        <article class="dv-card">
          <div class="dv-visual"><img src="{{ '/assets/img/long-term/smarp.png' | relative_url }}" alt="Magnetic Connectivity Tool"></div>
          <div class="dv-body">
            <h3><a href="https://connect-tool.irap.omp.eu/" target="_blank" rel="noopener">Magnetic Connectivity Tool</a></h3>
            <p>Connectivity mapping interface for locating likely solar source regions and tracing particle paths across spacecraft viewpoints.</p>
          </div>
        </article>

        <article class="dv-card">
          <div class="dv-visual"><img src="{{ '/assets/img/data-analysis/serpentine.png' | relative_url }}" alt="Propagation Tool"></div>
          <div class="dv-body">
            <h3><a href="https://propagationtool.cdpp.eu/" target="_blank" rel="noopener">Propagation Tool</a></h3>
            <p>Interactive heliospheric propagation visualizer used to inspect streams, shocks, and particle transport through interplanetary space.</p>
          </div>
        </article>

        <article class="dv-card">
          <div class="dv-visual"><img src="{{ '/assets/img/data-analysis/helioml.png' | relative_url }}" alt="Autoplot"></div>
          <div class="dv-body">
            <h3><a href="https://autoplot.org/" target="_blank" rel="noopener">Autoplot</a></h3>
            <p>Quick-look browser for local files and web data sources that turns raw tables and time series into readable plots with minimal setup.</p>
          </div>
        </article>
      </div>
    </section>
  </div>
</div>
