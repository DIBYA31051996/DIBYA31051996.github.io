---
layout: page
title: Space Based Instruments
permalink: /space-based/
nav: false
---

<style>
  .post-header .post-title,
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }

  .sb-shell {
    max-width: 1120px;
    margin: 0 auto;
    padding: 0.3rem 0 1rem;
  }

  .sb-panel {
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

  .sb-heading {
    text-align: center;
    margin-bottom: 1.5rem;
  }

  .sb-heading h1 {
    margin: 0;
    color: #f4f6fb;
    font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 800;
    letter-spacing: 0.04em;
  }

  .sb-rule {
    width: 100%;
    height: 3px;
    margin: 1rem 0 1.4rem;
    border-radius: 999px;
    background: linear-gradient(90deg, rgba(111, 157, 180, 0.88), rgba(111, 157, 180, 0.22));
  }

  .sb-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 1rem;
  }

  .sb-card {
    display: grid;
    grid-template-rows: 220px 1fr;
    min-height: 410px;
    border: 1px solid rgba(175, 194, 235, 0.16);
    border-radius: 20px;
    overflow: hidden;
    background:
      linear-gradient(180deg, rgba(16, 24, 43, 0.92), rgba(10, 17, 31, 0.96)),
      radial-gradient(circle at top right, rgba(88, 166, 255, 0.12), transparent 40%);
    box-shadow:
      0 14px 32px rgba(0, 0, 0, 0.18),
      inset 0 1px 0 rgba(255, 255, 255, 0.04);
    transition:
      transform 0.22s ease,
      box-shadow 0.22s ease,
      border-color 0.22s ease;
  }

  .sb-card:hover {
    transform: translateY(-4px);
    border-color: rgba(118, 196, 255, 0.48);
    box-shadow:
      0 18px 30px rgba(0, 0, 0, 0.22),
      0 0 0 1px rgba(118, 196, 255, 0.15),
      0 0 14px rgba(77, 173, 255, 0.08);
  }

  .sb-thumb {
    overflow: hidden;
    background:
      linear-gradient(180deg, rgba(243, 246, 255, 0.94), rgba(227, 234, 244, 0.94)),
      radial-gradient(circle at top right, rgba(88, 166, 255, 0.14), transparent 42%);
  }

  .sb-thumb img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    transition: transform 0.32s ease;
  }

  .sb-card:hover .sb-thumb img {
    transform: scale(1.02);
  }

  .sb-body {
    display: flex;
    flex-direction: column;
    padding: 1rem;
    background: linear-gradient(180deg, rgba(10, 17, 31, 0.98), rgba(8, 14, 28, 0.98));
  }

  .sb-body h3 {
    margin: 0 0 0.45rem;
    font-size: 1.08rem;
    line-height: 1.3;
    font-weight: 800;
    color: #f5f8fd;
  }

  .sb-body p {
    margin: 0;
    color: #d5def1;
    line-height: 1.62;
    font-size: 0.96rem;
  }

  .sb-body .sb-link {
    margin-top: auto;
    padding-top: 0.8rem;
  }

  .sb-body .sb-link a {
    color: #9dd2ff;
    text-decoration: none;
    font-weight: 700;
  }

  .sb-body .sb-link a:hover {
    color: #ffffff;
    text-decoration: underline;
  }

  @media (max-width: 980px) {
    .sb-grid {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }

  @media (max-width: 640px) {
    .sb-panel {
      padding: 1.2rem 0.9rem 1.5rem;
    }

    .sb-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="sb-shell">
  <div class="sb-panel">
    <div class="sb-heading">
      <h1>Space Based Instruments</h1>
      <div class="sb-rule"></div>
    </div>

    <div class="sb-grid">
      <article class="sb-card">
        <div class="sb-thumb"><img src="{{ '/assets/img/space-based/parker.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Parker Solar Probe"></div>
        <div class="sb-body">
          <h3>Parker Solar Probe</h3>
          <p>Mission designed to explore the Sun from the inner heliosphere and sample the near-Sun environment more closely than any previous mission.</p>
          <p class="sb-link"><a href="https://parkersolarprobe.jhuapl.edu/" target="_blank" rel="noopener">Official site</a></p>
        </div>
      </article>

      <article class="sb-card">
        <div class="sb-thumb"><img src="{{ '/assets/img/space-based/solar-orbiter.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Solar Orbiter"></div>
        <div class="sb-body">
          <h3>Solar Orbiter</h3>
          <p>ESA and NASA mission combining in-situ measurements and remote imaging to study the solar wind, corona, and polar perspectives of the Sun.</p>
          <p class="sb-link"><a href="https://www.esa.int/Science_Exploration/Space_Science/Solar_Orbiter" target="_blank" rel="noopener">Official site</a></p>
        </div>
      </article>

      <article class="sb-card">
        <div class="sb-thumb"><img src="{{ '/assets/img/space-based/sdo.png' | relative_url }}" loading="lazy" decoding="async" alt="Solar Dynamics Observatory"></div>
        <div class="sb-body">
          <h3>Solar Dynamics Observatory</h3>
          <p>Flagship observatory for high-cadence full-disk imaging and magnetic-field measurements across multiple solar atmosphere layers.</p>
          <p class="sb-link"><a href="https://sdo.gsfc.nasa.gov/" target="_blank" rel="noopener">Official site</a></p>
        </div>
      </article>

      <article class="sb-card">
        <div class="sb-thumb"><img src="{{ '/assets/img/space-based/soho.jpg' | relative_url }}" loading="lazy" decoding="async" alt="SOHO"></div>
        <div class="sb-body">
          <h3>SOHO - Solar and Heliospheric Observatory</h3>
          <p>Long-running ESA/NASA mission providing helioseismology, coronagraphy, and full-disk solar monitoring from the L1 point.</p>
          <p class="sb-link"><a href="https://soho.nascom.nasa.gov/" target="_blank" rel="noopener">Official site</a></p>
        </div>
      </article>

      <article class="sb-card">
        <div class="sb-thumb"><img src="{{ '/assets/img/space-based/rhessi.png' | relative_url }}" loading="lazy" decoding="async" alt="RHESSI"></div>
        <div class="sb-body">
          <h3>RHESSI</h3>
          <p>Mission focused on high-energy solar spectroscopy and imaging, central to flare and nonthermal emission studies.</p>
          <p class="sb-link"><a href="https://hesperia.gsfc.nasa.gov/rhessi3/" target="_blank" rel="noopener">Mission archive</a></p>
        </div>
      </article>

      <article class="sb-card">
        <div class="sb-thumb"><img src="{{ '/assets/img/space-based/stereo.png' | relative_url }}" loading="lazy" decoding="async" alt="STEREO"></div>
        <div class="sb-body">
          <h3>STEREO</h3>
          <p>Dual-spacecraft mission that provided stereoscopic views of the Sun and inner heliosphere for CME and coronal-structure studies.</p>
          <p class="sb-link"><a href="https://stereo.gsfc.nasa.gov/" target="_blank" rel="noopener">Official site</a></p>
        </div>
      </article>

      <article class="sb-card">
        <div class="sb-thumb"><img src="{{ '/assets/img/space-based/iris.png' | relative_url }}" loading="lazy" decoding="async" alt="IRIS"></div>
        <div class="sb-body">
          <h3>IRIS - Interface Region Imaging Spectrograph</h3>
          <p>High-resolution imaging spectrograph mission probing the chromosphere and transition region with fine temporal and spatial sampling.</p>
          <p class="sb-link"><a href="https://iris.lmsal.com/" target="_blank" rel="noopener">Official site</a></p>
        </div>
      </article>

      <article class="sb-card">
        <div class="sb-thumb"><img src="{{ '/assets/img/space-based/hinode.png' | relative_url }}" loading="lazy" decoding="async" alt="Hinode"></div>
        <div class="sb-body">
          <h3>Hinode</h3>
          <p>Mission dedicated to high-resolution solar imaging and spectroscopy, especially valuable for magnetic-field and coronal heating studies.</p>
          <p class="sb-link"><a href="https://sdc.uio.no/sdc/" target="_blank" rel="noopener">Official site</a></p>
        </div>
      </article>
    </div>
  </div>
</div>
