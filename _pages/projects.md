---
layout: page
title: Research
permalink: /projects/
description: Solar cycle and machine learning research directions.
nav: true
nav_order: 3
---

<style>
  .post-header .post-title,
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }
</style>

<div class="research-shell">
  <section class="research-frame">
    <aside class="research-sidebar">
      <div class="research-pill"><span class="research-pill-icon">◎</span> Home • Research</div>
      <h2>Research Areas</h2>

      <div class="research-nav" role="tablist" aria-label="Research areas">
        <a class="research-nav-btn active" href="#solar-cycle" data-target="solar-cycle" role="tab" aria-selected="true">
          <span class="research-nav-dot"></span>
          Solar Cycle
        </a>
        <a class="research-nav-btn" href="#machine-learning" data-target="machine-learning" role="tab" aria-selected="false">
          <span class="research-nav-dot"></span>
          Machine Learning
        </a>
      </div>
    </aside>

    <section class="research-content">
      <article class="research-panel active" data-panel="solar-cycle" role="tabpanel">
        <div class="research-heading">
          <h1>Solar Cycle</h1>
          <p>Long-term variability of solar magnetism and global field evolution</p>
        </div>

        <div class="research-copy">
          <p>
            I study the long-term evolution of solar magnetism across multiple cycles, focusing on cycle-to-cycle
            variability, polar-field diagnostics, and historical reconstructions that connect observations and modeling
            for space-weather relevant insights.
          </p>

          <h3>Solar Cycle Periodicity</h3>
          <p>
            This includes historical reconstruction, polar-field diagnostics, and links between surface magnetism and
            predictive space-weather indicators.
          </p>
        </div>

        <div class="research-detail-grid">
          <article class="research-detail-card">
            <h4>Typical questions</h4>
            <ul>
              <li>How do cycles differ in amplitude and timing?</li>
              <li>What do polar fields tell us about the next cycle?</li>
              <li>How far back can reconstructions be trusted?</li>
            </ul>
          </article>

          <article class="research-detail-card">
            <h4>Related sections</h4>
            <div class="research-actions">
              <a class="research-action-primary" href="{{ '/publications/' | relative_url }}">See publications</a>
              <a class="research-action-secondary" href="{{ '/blog/' | relative_url }}">Read article notes</a>
            </div>
          </article>
        </div>
      </article>

      <article class="research-panel" data-panel="machine-learning" role="tabpanel" hidden>
        <div class="research-heading">
          <h1>Machine Learning</h1>
          <p>Detection, classification, and reconstruction pipelines for archival solar observations</p>
        </div>

        <div class="research-copy">
          <p>
            My machine-learning work centers on building reliable pipelines for feature detection in century-long solar
            datasets, especially where archival material requires careful preprocessing, labeling, and interpretation.
          </p>

          <h3>Archival Intelligence</h3>
          <p>
            I use ML-oriented workflows for plage detection, solar-disk identification, pre-digital data reconstruction,
            and other tasks where automation can extend the scientific value of historical observations.
          </p>
        </div>

        <div class="research-detail-grid">
          <article class="research-detail-card">
            <h4>Typical questions</h4>
            <ul>
              <li>How can noisy archival data be made ML-ready?</li>
              <li>Which features are robust across decades of observations?</li>
              <li>Can learning-based methods recover structure from incomplete data?</li>
            </ul>
          </article>

          <article class="research-detail-card">
            <h4>Related sections</h4>
            <div class="research-actions">
              <a class="research-action-primary" href="{{ '/publications/' | relative_url }}">See publications</a>
              <a class="research-action-secondary" href="{{ '/repositories/' | relative_url }}">Open repositories</a>
            </div>
          </article>
        </div>
      </article>
    </section>
  </section>
</div>

<script>
document.addEventListener('DOMContentLoaded', function () {
  const buttons = Array.from(document.querySelectorAll('.research-nav-btn'));
  const panels = Array.from(document.querySelectorAll('.research-panel'));

  function showPanel(target) {
    buttons.forEach((button) => {
      const active = button.dataset.target === target;
      button.classList.toggle('active', active);
      button.setAttribute('aria-selected', active ? 'true' : 'false');
    });

    panels.forEach((panel) => {
      const active = panel.dataset.panel === target;
      panel.classList.toggle('active', active);
      panel.hidden = !active;
    });
  }

  buttons.forEach((button) => {
    button.addEventListener('click', function (event) {
      event.preventDefault();
      showPanel(button.dataset.target);
    });
  });
});
</script>
