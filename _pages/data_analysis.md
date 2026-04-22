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

  .da-title::before {
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
    padding: 0.9rem;
  }

  .da-body h3 {
    margin: 0 0 0.4rem;
    font-size: 1rem;
    line-height: 1.35;
    font-weight: 800;
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
          <div class="da-visual"><img src="{{ '/assets/img/space-based/sdo-logo.png' | relative_url }}" alt="SolarSoft"></div>
          <div class="da-body">
            <h3><a href="https://www.lmsal.com/solarsoft/" target="_blank" rel="noopener">SolarSoft</a></h3>
            <p>A broad IDL-based software environment for solar and heliophysics analysis workflows.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/long-term/solarmonitor-live.png' | relative_url }}" alt="SunPy"></div>
          <div class="da-body">
            <h3><a href="https://sunpy.org/" target="_blank" rel="noopener">SunPy</a></h3>
            <p>A Python package family for solar physics data access, map handling, and analysis.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/long-term/resource-forecast.svg' | relative_url }}" alt="MATLAB"></div>
          <div class="da-body">
            <h3><a href="https://www.mathworks.com/products/matlab.html" target="_blank" rel="noopener">MATLAB</a></h3>
            <p>Numerical computing software used for matrix-heavy analysis, modeling, and visualization.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/ground-based/radio-array.svg' | relative_url }}" alt="CASA"></div>
          <div class="da-body">
            <h3><a href="https://casa.nrao.edu/" target="_blank" rel="noopener">CASA</a></h3>
            <p>Radio astronomy analysis software maintained by NRAO for calibration and imaging workflows.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/long-term/resource-monitor.svg' | relative_url }}" alt="DS9"></div>
          <div class="da-body">
            <h3><a href="https://sites.google.com/cfa.harvard.edu/saoimageds9" target="_blank" rel="noopener">DS9</a></h3>
            <p>Widely used FITS image viewer for inspection, overlays, regions, and quick-look analysis.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/long-term/live-space-weather-status-live.jpeg' | relative_url }}" alt="Data Centers"></div>
          <div class="da-body">
            <h3><a href="https://sdc.uio.no/search/" target="_blank" rel="noopener">Data Centers</a></h3>
            <p>Searchable resource hubs for mission products, simulations, observations, and archives.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/long-term/solar-dynamo-user.jpg' | relative_url }}" alt="SuperMAG"></div>
          <div class="da-body">
            <h3><a href="https://supermag.jhuapl.edu/" target="_blank" rel="noopener">SuperMAG</a></h3>
            <p>Magnetometer network products useful for geospace context, comparison studies, and diagnostics.</p>
          </div>
        </article>

        <article class="da-card">
          <div class="da-visual"><img src="{{ '/assets/img/long-term/resource-archive.svg' | relative_url }}" alt="SunPy ML"></div>
          <div class="da-body">
            <h3><a href="https://docs.sunpy.org/projects/" target="_blank" rel="noopener">SunPy ML and Stats</a></h3>
            <p>Supporting Python tooling for machine-learning workflows, statistics, and reproducible analysis.</p>
          </div>
        </article>
      </div>
    </section>
  </div>
</div>
