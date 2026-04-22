---
layout: page
title: Ground Based Instruments
permalink: /ground-based/
nav: false
---

<style>
  .post-header .post-title,
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }

  .gb-shell {
    max-width: 1180px;
    margin: 0 auto;
    padding: 0.3rem 0 1rem;
  }

  .gb-panel {
    border-radius: 24px;
    padding: 1.8rem 1.5rem 2rem;
    background:
      radial-gradient(circle at top left, rgba(80, 146, 210, 0.16), transparent 24%),
      radial-gradient(circle at top right, rgba(41, 156, 112, 0.16), transparent 22%),
      linear-gradient(180deg, rgba(13, 20, 38, 0.96), rgba(8, 14, 28, 0.99));
    box-shadow:
      0 20px 44px rgba(0, 0, 0, 0.2),
      inset 0 1px 0 rgba(255, 255, 255, 0.08);
  }

  .gb-heading {
    text-align: center;
    margin-bottom: 1.4rem;
  }

  .gb-heading h1 {
    margin: 0 0 0.55rem;
    color: #f4f6fb;
    font-size: clamp(2.1rem, 4vw, 3.2rem);
    font-weight: 800;
    letter-spacing: 0.04em;
    text-shadow: 0 6px 22px rgba(77, 173, 255, 0.18);
  }

  .gb-heading p {
    margin: 0;
    color: #d0dcef;
    line-height: 1.6;
  }

  .gb-section + .gb-section {
    margin-top: 2rem;
  }

  .gb-section-title {
    margin: 0 0 1rem;
    color: #7f0b13;
    font-size: 1.7rem;
    font-weight: 800;
  }

  .gb-rule {
    width: 100%;
    height: 3px;
    margin: 0.6rem 0 1.1rem;
    border-radius: 999px;
    background: linear-gradient(90deg, rgba(111, 157, 180, 0.88), rgba(111, 157, 180, 0.22));
  }

  .gb-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 1rem;
    align-items: stretch;
  }

  .gb-card {
    display: flex;
    flex-direction: column;
    height: 100%;
    border: 1px solid rgba(175, 194, 235, 0.16);
    border-radius: 20px;
    overflow: hidden;
    background:
      linear-gradient(180deg, rgba(16, 24, 43, 0.9), rgba(10, 17, 31, 0.96)),
      radial-gradient(circle at top right, rgba(88, 166, 255, 0.12), transparent 40%);
    box-shadow:
      0 14px 32px rgba(0, 0, 0, 0.18),
      inset 0 1px 0 rgba(255, 255, 255, 0.04);
    transition:
      transform 0.22s ease,
      box-shadow 0.22s ease,
      border-color 0.22s ease;
  }

  .gb-thumb {
    flex: 0 0 clamp(220px, 18vw, 235px);
    height: clamp(220px, 18vw, 235px);
    display: grid;
    place-items: center;
    background:
      linear-gradient(180deg, rgba(243, 246, 255, 0.94), rgba(227, 234, 244, 0.94)),
      radial-gradient(circle at top right, rgba(88, 166, 255, 0.14), transparent 42%);
    color: #18324a;
    font-size: 3.4rem;
    font-weight: 800;
    letter-spacing: 0.06em;
  }

  .gb-thumb img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
    display: block;
    transition: transform 0.32s ease;
  }

  .gb-body {
    flex: 1 1 auto;
    min-height: 185px;
    display: flex;
    flex-direction: column;
    padding: 0.95rem 1rem 1.05rem;
  }

  .gb-body h3 {
    margin: 0 0 0.45rem;
    color: #f7f9fd;
    font-size: 1.08rem;
    font-weight: 800;
    line-height: 1.3;
    min-height: 3rem;
  }

  .gb-body p {
    margin: 0;
    color: #d5def1;
    line-height: 1.58;
    font-size: 0.97rem;
  }

  .gb-body p + p {
    margin-top: 0.55rem;
  }

  .gb-body p:not(.gb-link):first-of-type {
    min-height: 5.5rem;
  }

  .gb-body .gb-link {
    margin-top: auto;
    padding-top: 0.75rem;
  }

  .gb-section-optical .gb-card {
    display: grid;
    grid-template-rows: 235px 195px;
    min-height: 430px;
  }

  .gb-section-optical .gb-thumb {
    flex: none;
    height: 100%;
    overflow: hidden;
  }

  .gb-section-optical .gb-body {
    min-height: 195px;
    padding: 1rem 1rem 1rem;
    background: linear-gradient(180deg, rgba(10, 17, 31, 0.98), rgba(8, 14, 28, 0.98));
  }

  .gb-section-optical .gb-body h3 {
    min-height: 3.1rem;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .gb-section-optical .gb-body p:not(.gb-link):first-of-type {
    min-height: 0;
    display: -webkit-box;
    -webkit-line-clamp: 4;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .gb-section-microwave .gb-card {
    display: grid;
    grid-template-rows: 235px 195px;
    min-height: 430px;
  }

  .gb-section-microwave .gb-thumb {
    flex: none;
    height: 100%;
    overflow: hidden;
  }

  .gb-section-microwave .gb-body {
    min-height: 195px;
    padding: 1rem 1rem 1rem;
    background: linear-gradient(180deg, rgba(10, 17, 31, 0.98), rgba(8, 14, 28, 0.98));
  }

  .gb-section-microwave .gb-body h3 {
    min-height: 3.1rem;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .gb-section-microwave .gb-body p:not(.gb-link):first-of-type {
    min-height: 0;
    display: -webkit-box;
    -webkit-line-clamp: 4;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .gb-section-radio .gb-card {
    display: grid;
    grid-template-rows: 235px 195px;
    min-height: 430px;
  }

  .gb-section-radio .gb-thumb {
    flex: none;
    height: 100%;
    overflow: hidden;
  }

  .gb-section-radio .gb-body {
    min-height: 195px;
    padding: 1rem 1rem 1rem;
    background: linear-gradient(180deg, rgba(10, 17, 31, 0.98), rgba(8, 14, 28, 0.98));
  }

  .gb-section-radio .gb-body h3 {
    min-height: 3.1rem;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .gb-section-radio .gb-body p:not(.gb-link):first-of-type {
    min-height: 0;
    display: -webkit-box;
    -webkit-line-clamp: 4;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .gb-body a {
    color: #9dd2ff;
    text-decoration: none;
  }

  .gb-body a:hover {
    color: #ffffff;
    text-decoration: underline;
  }

  .gb-card:hover {
    transform: translateY(-4px);
    border-color: rgba(118, 196, 255, 0.52);
    box-shadow:
      0 18px 30px rgba(0, 0, 0, 0.24),
      0 0 0 1px rgba(118, 196, 255, 0.18),
      0 0 16px rgba(77, 173, 255, 0.1);
  }

  .gb-card:hover .gb-thumb img {
    transform: scale(1.02);
  }

  @media (max-width: 980px) {
    .gb-grid {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }

  @media (max-width: 640px) {
    .gb-panel {
      padding: 1.3rem 0.9rem 1.5rem;
    }

    .gb-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="gb-shell">
  <div class="gb-panel">
    <div class="gb-heading">
      <h1>Ground Based Instruments</h1>
      <p>
        A grouped view of major ground-based solar facilities from the categories shown in your reference:
        optical and synoptic telescopes, microwave and millimeter instruments, and radio observatories.
      </p>
    </div>

    <section class="gb-section gb-section-optical">
      <h2 class="gb-section-title">Optical and Synoptic</h2>
      <div class="gb-rule"></div>
      <div class="gb-grid">
        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/dkist.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Daniel K. Inouye Solar Telescope"></div>
          <div class="gb-body">
            <h3>DKIST - Daniel K. Inouye Solar Telescope</h3>
            <p>High-resolution solar facility designed to study the photosphere, chromosphere, and corona with unprecedented detail.</p>
            <p class="gb-link"><a href="https://nso.edu/dkist/data-center/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/gst.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Goode Solar Telescope"></div>
          <div class="gb-body">
            <h3>GST - Goode Solar Telescope</h3>
            <p>Big Bear Solar Observatory telescope used for high-resolution imaging and magnetic diagnostics of fine solar structure.</p>
            <p class="gb-link"><a href="https://www.bbso.njit.edu/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/gregor.jpg' | relative_url }}" loading="lazy" decoding="async" alt="GREGOR Solar Telescope"></div>
          <div class="gb-body">
            <h3>GREGOR Solar Telescope</h3>
            <p>European ground-based solar telescope focused on magnetic fields, fine-scale solar dynamics, and spectropolarimetry.</p>
            <p class="gb-link"><a href="https://www.leibniz-kis.de/en/observatories/gregor/access-to-gregor-data/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/dst.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Dunn Solar Telescope"></div>
          <div class="gb-body">
            <h3>DST - Dunn Solar Telescope</h3>
            <p>Long-running U.S. solar telescope known for adaptive-optics observations and detailed measurements of active regions.</p>
            <p class="gb-link"><a href="https://nso.edu/telescopes/dunn-solar-telescope/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/kso.jpeg' | relative_url }}" loading="lazy" decoding="async" alt="Kodaikanal Solar Observatory"></div>
          <div class="gb-body">
            <h3>KSO - Kodaikanal Solar Observatory</h3>
            <p>Historic solar observatory with long-baseline synoptic records central to cycle-scale studies and archival context.</p>
            <p class="gb-link"><a href="https://kso.iiap.res.in/new" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/sst.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Swedish Solar Telescope"></div>
          <div class="gb-body">
            <h3>SST - Swedish Solar Telescope</h3>
            <p>High-resolution telescope widely used for small-scale photospheric and chromospheric structure studies.</p>
            <p class="gb-link"><a href="https://www.isf.astro.su.se/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/dot.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Dutch Open Telescope"></div>
          <div class="gb-body">
            <h3>DOT - Dutch Open Telescope</h3>
            <p>Open-design solar telescope at La Palma, known for high-resolution imaging and multi-wavelength solar studies.</p>
            <p class="gb-link"><a href="https://www.staff.science.uu.nl/~rutte101/DOT/" target="_blank" rel="noopener">Project site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/hida.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Hida Observatory"></div>
          <div class="gb-body">
            <h3>HIDA Observatory</h3>
            <p>Japanese solar observing facility associated with high-resolution spectroscopy and long-running solar studies.</p>
            <p class="gb-link"><a href="https://www.hida.kyoto-u.ac.jp/SMART/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/mast.jpg' | relative_url }}" loading="lazy" decoding="async" alt="MAST at Udaipur Solar Observatory"></div>
          <div class="gb-body">
            <h3>MAST - Multi-Application Solar Telescope</h3>
            <p>Off-axis solar telescope at Udaipur Solar Observatory built for high-resolution studies of solar magnetic activity.</p>
            <p class="gb-link"><a href="https://www.prl.res.in/~usodataarchive/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/gong.jpg' | relative_url }}" loading="lazy" decoding="async" alt="GONG related observatory"></div>
          <div class="gb-body">
            <h3>GONG - Global Oscillation Network Group</h3>
            <p>Synoptic network used for helioseismology, full-disk magnetic field products, and solar dynamical studies.</p>
            <p class="gb-link"><a href="https://gong.nso.edu/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>
      </div>
    </section>

    <section class="gb-section gb-section-microwave">
      <h2 class="gb-section-title">Microwave and Millimeter</h2>
      <div class="gb-rule"></div>
      <div class="gb-grid">
        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/alma.jpg' | relative_url }}" loading="lazy" decoding="async" alt="ALMA observatory"></div>
          <div class="gb-body">
            <h3>ALMA</h3>
            <p>Millimeter and sub-millimeter observations of the solar atmosphere, especially useful for chromospheric diagnostics.</p>
            <p class="gb-link"><a href="https://www.almaobservatory.org/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/norh.jpg' | relative_url }}" loading="lazy" decoding="async" alt="Nobeyama Radioheliograph"></div>
          <div class="gb-body">
            <h3>NoRH - Nobeyama Radioheliograph</h3>
            <p>Long-running microwave facility that tracks the Sun at 17 and 34 GHz, including flare and active-region evolution.</p>
            <p class="gb-link"><a href="https://solar.nro.nao.ac.jp/norh/html/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/ratan600.gif' | relative_url }}" loading="lazy" decoding="async" alt="RATAN-600"></div>
          <div class="gb-body">
            <h3>RATAN-600</h3>
            <p>Large radio telescope with solar observing capability used for spectral and magnetic diagnostics.</p>
            <p class="gb-link"><a href="https://www.sao.ru/hq/sun/latest.htm" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/eovsa.jpg' | relative_url }}" loading="lazy" decoding="async" alt="EOVSA"></div>
          <div class="gb-body">
            <h3>EOVSA</h3>
            <p>Microwave interferometer used to probe flare energy release and coronal magnetic structure.</p>
            <p class="gb-link"><a href="https://www.ovsa.njit.edu/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/ssrt.png' | relative_url }}" loading="lazy" decoding="async" alt="SRH or SSRT"></div>
          <div class="gb-body">
            <h3>SRH / SSRT</h3>
            <p>Solar radio imaging instruments used for dynamic event monitoring and full-disk radio context.</p>
            <p class="gb-link"><a href="https://badary.iszf.irk.ru/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/mro.png' | relative_url }}" loading="lazy" decoding="async" alt="MRO radio observatory"></div>
          <div class="gb-body">
            <h3>MRO (11.2 GHz, 37 GHz)</h3>
            <p>Microwave radio observations in dedicated bands used for activity monitoring and flare-related diagnostics.</p>
            <p class="gb-link"><a href="https://www.metsahovi.fi/sun/data/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/sundish.png' | relative_url }}" loading="lazy" decoding="async" alt="Sundish radio telescope"></div>
          <div class="gb-body">
            <h3>Sundish (18 - 26 GHz)</h3>
            <p>Microwave Sun-as-a-star style radio measurements useful for tracking variability in the centimeter band.</p>
            <p class="gb-link"><a href="https://sites.google.com/inaf.it/sundish/sundish-images-archive/sundish-solar-archive?authuser=0" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>
      </div>
    </section>

    <section class="gb-section gb-section-radio">
      <h2 class="gb-section-title">Radio</h2>
      <div class="gb-rule"></div>
      <div class="gb-grid">
        <article class="gb-card">
          <div class="gb-thumb"><img src="https://www.astron.nl/wp-content/uploads/2020/05/header_lofar-scaled-e1589880886578.jpg" loading="lazy" decoding="async" alt="LOFAR solar observations"></div>
          <div class="gb-body">
            <h3>LOFAR</h3>
            <p>Low-frequency radio observations of the Sun used to study the corona, bursts, and propagation effects.</p>
            <p class="gb-link"><a href="https://www.lofar.org/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="https://www.obs-nancay.fr/wp-content/uploads/2025/04/Observatoire_de_Paris-CoMarquageORN-RGB-Noir_sideral-scaled-1.jpg" loading="lazy" decoding="async" alt="Nancay Radioheliograph"></div>
          <div class="gb-body">
            <h3>Nancay Radioheliograph</h3>
            <p>Well-known radioheliograph for imaging solar radio activity and large-scale coronal signatures.</p>
            <p class="gb-link"><a href="https://solar.nro.nao.ac.jp/norh/html/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>

        <article class="gb-card">
          <div class="gb-thumb"><img src="{{ '/assets/img/ground-based/ecallisto.png' | relative_url }}" loading="lazy" decoding="async" alt="e-CALLISTO"></div>
          <div class="gb-body">
            <h3>e-CALLISTO</h3>
            <p>Global network of low-cost radio spectrometers used to monitor solar radio bursts around the world.</p>
            <p class="gb-link"><a href="https://www.e-callisto.org/" target="_blank" rel="noopener">Official site</a></p>
          </div>
        </article>
      </div>
    </section>
  </div>
</div>
