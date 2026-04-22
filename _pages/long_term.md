---
layout: page
title: Long-Term Monitoring and Forecast
permalink: /long-term/
nav: false
---

<style>
  .post-header .post-title,
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }

  .lt-shell {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0.3rem 0 1rem;
  }

  .lt-panel {
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

  .lt-heading {
    text-align: center;
    margin-bottom: 1.6rem;
  }

  .lt-heading h1 {
    margin: 0;
    color: #f4f6fb;
    font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 800;
    letter-spacing: 0.04em;
    text-shadow: 0 6px 22px rgba(77, 173, 255, 0.18);
  }

  .lt-heading p {
    margin: 0.75rem auto 0;
    max-width: 760px;
    color: #d0dcef;
    line-height: 1.7;
  }

  .lt-rule {
    width: 100%;
    height: 3px;
    margin: 1rem 0 1.5rem;
    border-radius: 999px;
    background: linear-gradient(90deg, rgba(111, 157, 180, 0.88), rgba(111, 157, 180, 0.22));
  }

  .lt-list {
    display: grid;
    gap: 1rem;
  }

  .lt-card {
    display: grid;
    grid-template-columns: 370px minmax(0, 1fr);
    gap: 1rem;
    align-items: stretch;
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

  .lt-card img {
    width: 100%;
    height: 100%;
    min-height: 235px;
    object-fit: cover;
    display: block;
    transition: transform 0.32s ease;
  }

  .lt-body {
    display: flex;
    flex-direction: column;
    padding: 1rem 1rem 1rem 0;
  }

  .lt-body h3 {
    margin: 0 0 0.45rem;
    font-size: 1.25rem;
    line-height: 1.3;
    font-weight: 800;
  }

  .lt-body h3 a {
    color: #b8e1ff;
    text-decoration: none;
  }

  .lt-body h3 a:hover {
    color: #ffffff;
    text-decoration: underline;
  }

  .lt-body p {
    margin: 0;
    color: #d4deef;
    line-height: 1.65;
  }

  .lt-body .lt-link {
    margin-top: auto;
    padding-top: 0.8rem;
  }

  .lt-body .lt-link a {
    color: #9dd2ff;
    text-decoration: none;
    font-weight: 700;
  }

  .lt-body .lt-link a:hover {
    color: #ffffff;
    text-decoration: underline;
  }

  .lt-card:hover {
    transform: translateY(-4px);
    border-color: rgba(118, 196, 255, 0.52);
    box-shadow:
      0 14px 24px rgba(0, 0, 0, 0.18),
      0 0 0 1px rgba(118, 196, 255, 0.18),
      0 0 12px rgba(77, 173, 255, 0.08);
  }

  .lt-card:hover img,
  .lt-mini-card:hover img {
    transform: scale(1.012);
  }

  .lt-subtitle {
    margin: 2rem 0 1rem;
    display: inline-flex;
    align-items: center;
    gap: 0.58rem;
    color: #f5fbff;
    font-size: 1.2rem;
    font-weight: 800;
    letter-spacing: 0.04em;
    text-shadow: 0 0 16px rgba(103, 194, 255, 0.18);
  }

  .lt-subtitle::before {
    content: "";
    width: 0.68rem;
    height: 0.68rem;
    border-radius: 999px;
    background: linear-gradient(135deg, #71ddff 0%, #7d8dff 100%);
    box-shadow: 0 0 14px rgba(113, 221, 255, 0.5);
  }

  .lt-mini-grid {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    gap: 1rem;
  }

  .lt-mini-card {
    border: 1px solid rgba(175, 194, 235, 0.16);
    border-radius: 18px;
    overflow: hidden;
    background:
      linear-gradient(180deg, rgba(16, 24, 43, 0.92), rgba(10, 17, 31, 0.96)),
      radial-gradient(circle at top right, rgba(88, 166, 255, 0.12), transparent 40%);
    transition:
      transform 0.22s ease,
      box-shadow 0.22s ease,
      border-color 0.22s ease;
  }

  .lt-mini-card img {
    width: 100%;
    height: 170px;
    object-fit: cover;
    display: block;
    transition: transform 0.32s ease;
  }

  .lt-mini-card .lt-mini-body {
    padding: 0.9rem;
  }

  .lt-mini-card h4 {
    margin: 0 0 0.4rem;
    font-size: 1rem;
    line-height: 1.35;
    font-weight: 800;
  }

  .lt-mini-card h4 a {
    color: #b8e1ff;
    text-decoration: none;
  }

  .lt-mini-card h4 a:hover {
    color: #ffffff;
    text-decoration: underline;
  }

  .lt-mini-card:hover {
    transform: translateY(-4px);
    border-color: rgba(118, 196, 255, 0.48);
    box-shadow:
      0 12px 22px rgba(0, 0, 0, 0.16),
      0 0 0 1px rgba(118, 196, 255, 0.14),
      0 0 10px rgba(77, 173, 255, 0.08);
  }

  .lt-mini-card p {
    margin: 0;
    color: #d4deef;
    line-height: 1.55;
    font-size: 0.94rem;
  }

  @media (max-width: 900px) {
    .lt-card {
      grid-template-columns: 1fr;
      gap: 0;
    }

    .lt-body {
      padding: 1rem;
    }

    .lt-mini-grid {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }

  @media (max-width: 640px) {
    .lt-panel {
      padding: 1.2rem 0.9rem 1.5rem;
    }

    .lt-mini-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="lt-shell">
  <div class="lt-panel">
    <div class="lt-heading">
      <h1>Long-Term Monitoring &amp; Forecast</h1>
      <div class="lt-rule"></div>
      <p>
        A compact directory of long-term monitoring, forecast, and archival resources useful for solar activity context,
        space-weather tracking, and multi-cycle reference work.
      </p>
    </div>

    <div class="lt-list">
      <article class="lt-card">
        <img src="{{ '/assets/img/long-term/solarmonitor-live.png' | relative_url }}" loading="lazy" decoding="async" alt="SolarMonitor">
        <div class="lt-body">
          <h3><a href="https://www.solarmonitor.org/" target="_blank" rel="noopener">SolarMonitor</a></h3>
          <p>This resource combines near-real-time and archive views of active regions, events, images, and solar-weather context products in one place.</p>
          <p class="lt-link"><a href="https://www.solarmonitor.org/" target="_blank" rel="noopener">Open resource</a></p>
        </div>
      </article>

      <article class="lt-card">
        <img src="https://helioviewer.org/resources/images/logos/hvlogo1s_transparent.png" loading="lazy" decoding="async" alt="HelioViewer">
        <div class="lt-body">
          <h3><a href="https://helioviewer.org/" target="_blank" rel="noopener">HelioViewer</a></h3>
          <p>HelioViewer provides quick visual access to multi-mission solar imagery with interactive browsing, overlays, and movie generation for event context.</p>
          <p class="lt-link"><a href="https://helioviewer.org/" target="_blank" rel="noopener">Open resource</a></p>
        </div>
      </article>

      <article class="lt-card">
        <img src="{{ '/assets/img/long-term/silso.png' | relative_url }}" loading="lazy" decoding="async" alt="SIDC-SILSO">
        <div class="lt-body">
          <h3><a href="https://www.sidc.be/SILSO/" target="_blank" rel="noopener">SIDC-SILSO</a></h3>
          <p>The SILSO sunspot-number database provides daily, monthly, and long-term indices that are central to solar-cycle monitoring and reconstruction work.</p>
          <p class="lt-link"><a href="https://www.sidc.be/SILSO/" target="_blank" rel="noopener">Open resource</a></p>
        </div>
      </article>

      <article class="lt-card">
        <img src="https://images-assets.nasa.gov/image/PIA21949/PIA21949~orig.jpg" loading="lazy" decoding="async" alt="Solar cycle forecast">
        <div class="lt-body">
          <h3><a href="https://www.nasa.gov/msfcsolar/datasources" target="_blank" rel="noopener">Marshall Solar Cycle Forecast</a></h3>
          <p>Solar-cycle progression plots and forecast context from operational space-weather resources, useful for broad cycle-phase interpretation.</p>
          <p class="lt-link"><a href="https://www.nasa.gov/msfcsolar/datasources" target="_blank" rel="noopener">Open resource</a></p>
        </div>
      </article>

      <article class="lt-card">
        <img src="https://services.swpc.noaa.gov/images/animations/suvi/primary/195/latest.png" loading="lazy" decoding="async" alt="Space Weather Prediction Center">
        <div class="lt-body">
          <h3><a href="https://www.swpc.noaa.gov/" target="_blank" rel="noopener">Space Weather Prediction Center</a></h3>
          <p>A comprehensive source of operational space-weather data, products, alerts, forecast summaries, and environment maps.</p>
          <p class="lt-link"><a href="https://www.swpc.noaa.gov/" target="_blank" rel="noopener">Open resource</a></p>
        </div>
      </article>

      <article class="lt-card">
        <img src="{{ '/assets/img/long-term/australian-space-weather-live.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Australian Space Weather database">
        <div class="lt-body">
          <h3><a href="https://www.sws.bom.gov.au/" target="_blank" rel="noopener">Australian Space Weather Database</a></h3>
          <p>Australian space-weather products, reports, and event summaries for operational monitoring and archive reference.</p>
          <p class="lt-link"><a href="https://www.sws.bom.gov.au/" target="_blank" rel="noopener">Open resource</a></p>
        </div>
      </article>

      <article class="lt-card">
        <img src="{{ '/assets/img/long-term/canadian-space-weather.png' | relative_url }}" loading="lazy" decoding="async" alt="Canadian Space Weather Database">
        <div class="lt-body">
          <h3><a href="https://www.spaceweather.gc.ca/" target="_blank" rel="noopener">Canadian Space Weather Database</a></h3>
          <p>Canadian geospace and space-weather observations, services, and data access for geomagnetic and radio-environment context.</p>
          <p class="lt-link"><a href="https://www.spaceweather.gc.ca/" target="_blank" rel="noopener">Open resource</a></p>
        </div>
      </article>

      <article class="lt-card">
        <img src="https://kp.gfz-potsdam.de/typo3conf/ext/kp_index_sitepackage/Resources/Public/Images/logo_ISGI.gif" loading="lazy" decoding="async" alt="Geomagnetic Kp index">
        <div class="lt-body">
          <h3><a href="https://kp.gfz-potsdam.de/en/" target="_blank" rel="noopener">Geomagnetic Kp Index</a></h3>
          <p>The definitive Kp and ap geomagnetic indices for monitoring magnetospheric variability and solar-terrestrial conditions.</p>
          <p class="lt-link"><a href="https://kp.gfz-potsdam.de/en/" target="_blank" rel="noopener">Open resource</a></p>
        </div>
      </article>

      <article class="lt-card">
        <img src="https://images-assets.nasa.gov/image/PIA21949/PIA21949~orig.jpg" loading="lazy" decoding="async" alt="Solar Active Region Compilation">
        <div class="lt-body">
          <h3><a href="https://www.nasa.gov/solar-cycle-progression-and-forecast/" target="_blank" rel="noopener">Solar Active Region Compilation</a></h3>
          <p>Daily and historical active-region listings with identifiers and compact summaries useful for event cross-reference work.</p>
          <p class="lt-link"><a href="https://www.nasa.gov/solar-cycle-progression-and-forecast/" target="_blank" rel="noopener">Open resource</a></p>
        </div>
      </article>

      <article class="lt-card">
        <img src="https://services.swpc.noaa.gov/images/animations/suvi/primary/304/latest.png" loading="lazy" decoding="async" alt="Solar flare catalog compilation">
        <div class="lt-body">
          <h3><a href="https://www.ngdc.noaa.gov/stp/space-weather/solar-data/solar-features/solar-flares/" target="_blank" rel="noopener">Solar Flare Catalog Compilation</a></h3>
          <p>Flare listings and long-baseline event compilations that support event-based studies and historical comparisons.</p>
          <p class="lt-link"><a href="https://www.ngdc.noaa.gov/stp/space-weather/solar-data/solar-features/solar-flares/" target="_blank" rel="noopener">Open resource</a></p>
        </div>
      </article>
    </div>

    <h2 class="lt-subtitle">Other Resources</h2>
    <div class="lt-mini-grid">
      <article class="lt-mini-card">
        <img src="{{ '/assets/img/long-term/gong-logo.jpg' | relative_url }}" loading="lazy" decoding="async" alt="GONG Data Archive">
        <div class="lt-mini-body">
          <h4><a href="https://gong.nso.edu/data/" target="_blank" rel="noopener">GONG Data Archive</a></h4>
          <p>Synoptic full-disk observations and long-running helioseismic products from the GONG network.</p>
        </div>
      </article>

      <article class="lt-mini-card">
        <img src="{{ '/assets/img/long-term/live-space-weather-status-live.jpeg' | relative_url }}" loading="lazy" decoding="async" alt="Live Space Weather Status">
        <div class="lt-mini-body">
          <h4><a href="https://sites.google.com/view/indus-solphys/resources/data-tools/long-term-monitoring-forecast?authuser=0#h.plk9in92xt88" target="_blank" rel="noopener">Live Space Weather Status</a></h4>
          <p>A broad operational dashboard for solar, heliospheric, and geospace context.</p>
        </div>
      </article>

      <article class="lt-mini-card">
        <img src="{{ '/assets/img/long-term/solar-dynamo-user.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Solar Dynamo Dataverse">
        <div class="lt-mini-body">
          <h4><a href="https://dataverse.harvard.edu/dataverse/solardynamo" target="_blank" rel="noopener">Solar Dynamo Dataverse</a></h4>
          <p>A collective of databases and products tailored to understanding and predicting the solar cycle.</p>
        </div>
      </article>

      <article class="lt-mini-card">
        <img src="{{ '/assets/img/long-term/solar-activity-user.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Solar activity reconstruction">
        <div class="lt-mini-body">
          <h4><a href="https://www2.mps.mpg.de/projects/sun-climate/data.html" target="_blank" rel="noopener">Solar Activity Reconstruction</a></h4>
          <p>Solar cyclic activity over the last millennium reconstructed from annual proxy records.</p>
        </div>
      </article>

      <article class="lt-mini-card">
        <img src="https://static.arxiv.org/icons/twitter/arxiv-logo-twitter-square.png" loading="lazy" decoding="async" alt="SMARPs and SHARPs">
        <div class="lt-mini-body">
          <h4><a href="https://arxiv.org/abs/2108.07918?s=08" target="_blank" rel="noopener">SMARPs and SHARPs</a></h4>
          <p>Active-region data products supporting machine-learning studies and solar cycle 23-24 investigations.</p>
        </div>
      </article>

      <article class="lt-mini-card">
        <img src="{{ '/assets/img/long-term/vizier.gif' | relative_url }}" loading="lazy" decoding="async" alt="VizieR Online Data Catalog">
        <div class="lt-mini-body">
          <h4><a href="https://cdsarc.cds.unistra.fr/" target="_blank" rel="noopener">VizieR Online Data Catalog</a></h4>
          <p>Historic solar and astrophysical catalogs, including sunspot, faculae, and prominence datasets.</p>
        </div>
      </article>

      <article class="lt-mini-card">
        <img src="{{ '/assets/img/long-term/sunspot-chart-user.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Sunspot Observations in 1719-1720">
        <div class="lt-mini-body">
          <h4><a href="https://link.springer.com/article/10.1007/s11207-020-01706-z" target="_blank" rel="noopener">Sunspot Observations in 1719-1720</a></h4>
          <p>Early telescopic observations that help extend the long-baseline record of solar activity.</p>
        </div>
      </article>

      <article class="lt-mini-card">
        <img src="{{ '/assets/img/long-term/solis.jpg' | relative_url }}" loading="lazy" decoding="async" alt="SOLIS Data Product">
        <div class="lt-mini-body">
          <h4><a href="https://solis.nso.edu/0/solis_data.html" target="_blank" rel="noopener">SOLIS Data Product</a></h4>
          <p>Integrated synoptic magnetogram and dopplergram products from the SOLIS program.</p>
        </div>
      </article>
    </div>
  </div>
</div>
