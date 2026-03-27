---
layout: page
title: about
permalink: /
nav: false
---

<style>
  .hero-wrap {
    padding: 1.2rem;
    border-radius: 18px;
    border: 1px solid rgba(255,255,255,.16);
    background:
      radial-gradient(1100px 500px at -5% -15%, rgba(115,81,255,.35), transparent 55%),
      radial-gradient(900px 430px at 105% 0%, rgba(0,167,138,.24), transparent 48%),
      #070d1d;
    color: #dce5ff;
  }

  .hero-top {
    display: inline-flex;
    border: 1px solid rgba(255,255,255,.18);
    border-radius: 999px;
    padding: .45rem .9rem;
    background: rgba(255,255,255,.05);
    margin-bottom: 1rem;
  }

  .hero-grid {
    display: grid;
    grid-template-columns: 1.7fr 1fr;
    gap: 1rem;
  }

  .hero-left,
  .hero-right,
  .mini-card,
  .journey,
  .highlight-box {
    border: 1px solid rgba(255,255,255,.14);
    border-radius: 16px;
    background: linear-gradient(140deg, rgba(255,255,255,.09), rgba(255,255,255,.03));
    backdrop-filter: blur(2px);
  }

  .hero-left { padding: 1rem; }
  .hero-left h1 { margin-top: 0; color: #f7fbff; font-size: 2.1rem; }
  .hero-left h1 span { color: #5ea8ff; }
  .hero-left p { color: #cbd6f7; font-size: 1.18rem; }

  .action-row { display: flex; gap: .65rem; flex-wrap: wrap; margin: 1rem 0; }
  .btnx {
    border: 1px solid rgba(255,255,255,.2);
    border-radius: 12px;
    padding: .55rem 1rem;
    text-decoration: none;
    color: #dce5ff;
    background: rgba(10,17,36,.7);
  }
  .btnx.primary {
    border-color: transparent;
    background: linear-gradient(90deg,#8156ff,#2b8cff);
    color: #fff;
  }

  .mini-grid {
    display: grid;
    grid-template-columns: repeat(3,minmax(100px,1fr));
    gap: .65rem;
  }
  .mini-card { padding: .8rem; }
  .mini-card strong { display: block; color: #fff; font-size: 1.4rem; }
  .mini-card span { color: #bac8ef; }

  .journey { padding: 1rem; margin-top: .8rem; }
  .journey h3 { color: #fff; margin-top: 0; }

  .hero-right { padding: .8rem; }
  .hero-right img { width: 100%; border-radius: 12px; margin-bottom: .65rem; }
  .hero-right h3 { margin: .2rem 0; color: #fff; }
  .hero-right p { color: #b8c6ee; }

  .pill-row { display: flex; gap: .5rem; flex-wrap: wrap; margin-top: .5rem; }
  .pill-row a {
    border: 1px solid rgba(255,255,255,.2);
    border-radius: 999px;
    padding: .35rem .8rem;
    text-decoration: none;
    color: #dce5ff;
  }

  .highlight-box { padding: .9rem; margin-top: .9rem; }
  .highlight-box h3 { margin-top: 0; color: #fff; }

  @media (max-width: 980px) {
    .hero-grid { grid-template-columns: 1fr; }
    .mini-grid { grid-template-columns: 1fr; }
    .hero-left h1 { font-size: 1.75rem; }
    .hero-left p { font-size: 1rem; }
  }
</style>

<div class="hero-wrap">
  <div class="hero-top">🟢 Solar physicist • Data-driven heliophysics</div>

  <div class="hero-grid">
    <section class="hero-left">
      <h1>Dibya <span>Kirti Mishra</span></h1>
      <p>
        I study how solar magnetic fields evolve across cycles and how this evolution shapes
        space-weather prediction and long-baseline solar datasets.
      </p>

      <div class="action-row">
        <a class="btnx primary" href="/projects/">Explore Research</a>
        <a class="btnx" href="/publications/">Browse Publications</a>
        <a class="btnx" href="/repositories/">GitHub</a>
      </div>

      <div class="mini-grid">
        <div class="mini-card"><strong>38</strong><span>Refereed publications</span></div>
        <div class="mini-card"><strong>6</strong><span>Active research themes</span></div>
        <div class="mini-card"><strong>ARIES</strong><span>Current research base</span></div>
      </div>

      <article class="journey">
        <h3>Research focus</h3>
        <p>
          I work on long-term solar activity, sunspot/chromospheric analysis, and machine-learning
          methods for automated feature extraction and cycle-scale forecasting.
        </p>
      </article>
    </section>

    <aside>
      <div class="hero-right">
        <img src="/assets/img/prof_pic.jpg" alt="Dibya Kirti Mishra" />
        <h3>Dibya Kirti Mishra</h3>
        <p>Senior Research Fellow • ARIES, Nainital</p>
        <div class="pill-row">
          <a href="mailto:dibyakirtimishra@gmail.com">Connect</a>
          <a href="/projects/">Research</a>
          <a href="/publications/">Publications</a>
        </div>
      </div>

      <div class="highlight-box">
        <h3>Recent highlights</h3>
        <p>Century-scale solar records for improved cycle prediction.</p>
        <p>Data-driven image workflows for feature tracking.</p>
      </div>
    </aside>
  </div>
</div>
