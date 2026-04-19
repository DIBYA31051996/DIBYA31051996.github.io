---
layout: page
permalink: /repositories/
title: Repositories
description: Code, tools, and research repositories.
nav: true
nav_order: 6
---

<style>
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }
</style>

<div class="repo-shell">
  <section class="repo-hero repo-panel">
    <div class="repo-hero-copy">
      <div class="repo-pill">Code Archive</div>
      <h1>Repositories and tools</h1>
      <p>
        A small collection of research software, datasets, and website code that supports my work in solar physics,
        long-baseline observations, and data-driven analysis.
      </p>
    </div>
    <div class="repo-hero-meta">
      <div class="repo-meta-card">
        <strong>{{ site.data.repositories.github_repos.size }}</strong>
        <span>Featured repositories</span>
      </div>
      <div class="repo-meta-card">
        <strong>{{ site.data.repositories.github_users.size }}</strong>
        <span>GitHub profile</span>
      </div>
    </div>
  </section>

  {% if site.data.repositories.github_users %}
    <section class="repo-panel">
      <div class="repo-section-heading">
        <h2>GitHub profile</h2>
        <p>A direct entry point to my public code, releases, and ongoing work on GitHub.</p>
      </div>
      <div class="repo-profile-spotlight">
        {% for user in site.data.repositories.github_users %}
          <article class="repo-profile-card">
            <div class="repo-profile-mark">@</div>
            <div class="repo-profile-copy">
              <h3>{{ user }}</h3>
              <p>Research code, data tools, and website development collected in one place.</p>
            </div>
            <div class="repo-profile-actions">
              <a class="repo-link-btn" href="https://github.com/{{ user }}" target="_blank" rel="noopener">Open GitHub</a>
            </div>
          </article>
        {% endfor %}
      </div>
    </section>
  {% endif %}

  {% if site.data.repositories.github_repos %}
    <section class="repo-panel">
      <div class="repo-section-heading">
        <h2>Featured repositories</h2>
        <p>Selected codebases related to software, datasets, and the structure of this website.</p>
      </div>
      <div class="repo-card-grid">
        {% for repo in site.data.repositories.github_repos %}
          {% assign repo_parts = repo | split: '/' %}
          {% assign repo_name = repo_parts[1] %}
          <article class="repo-showcase-card">
            <div class="repo-showcase-top">
              <div class="repo-type-pill">
                {% case repo_name %}
                  {% when 'scoobi' %}Software
                  {% when 'kosopni' %}Dataset
                  {% else %}Website
                {% endcase %}
              </div>
              <h3>{{ repo_name }}</h3>
              <p class="repo-slug">{{ repo }}</p>
            </div>

            <p class="repo-summary">
              {% case repo_name %}
                {% when 'scoobi' %}
                  Solar analysis utilities and workflow-oriented code for handling observational data products.
                {% when 'kosopni' %}
                  Repository connected to long-baseline polar network index data and supporting project material.
                {% else %}
                  Source code for this personal website, including layout, styling, and content structure.
              {% endcase %}
            </p>

            <div class="repo-tag-row">
              {% case repo_name %}
                {% when 'scoobi' %}
                  <span>Python</span><span>Workflow</span><span>Solar tools</span>
                {% when 'kosopni' %}
                  <span>Data</span><span>Archive</span><span>Solar cycle</span>
                {% else %}
                  <span>Jekyll</span><span>Design</span><span>Portfolio</span>
              {% endcase %}
            </div>

            <div class="repo-actions-row">
              <a class="repo-link-btn" href="https://github.com/{{ repo }}" target="_blank" rel="noopener">Repository</a>
              <a class="repo-link-btn repo-link-btn-soft" href="https://github.com/{{ repo }}#readme" target="_blank" rel="noopener">Readme</a>
            </div>
          </article>
        {% endfor %}
      </div>
    </section>
  {% endif %}
</div>
