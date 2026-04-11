---
layout: page
permalink: /repositories/
title: Repositories
description: Code, tools, and research repositories.
nav: true
nav_order: 4
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
        <p>The main profile card gives a quick overview of activity, languages, and repository footprint.</p>
      </div>
      <div class="repo-grid repo-grid-profile">
        {% for user in site.data.repositories.github_users %}
          {% include repository/repo_user.liquid username=user %}
        {% endfor %}
      </div>
    </section>
  {% endif %}

  {% if site.data.repositories.github_repos %}
    <section class="repo-panel">
      <div class="repo-section-heading">
        <h2>Featured repositories</h2>
        <p>Selected codebases related to tools, data products, and the site itself.</p>
      </div>
      <div class="repo-grid repo-grid-projects">
        {% for repo in site.data.repositories.github_repos %}
          {% include repository/repo.liquid repository=repo %}
        {% endfor %}
      </div>
    </section>
  {% endif %}

  {% if site.repo_trophies.enabled and site.data.repositories.github_users %}
    {% for user in site.data.repositories.github_users %}
      <section class="repo-panel">
        <div class="repo-section-heading">
          <h2>Contribution highlights</h2>
          <p>A quick visual snapshot of long-term GitHub activity and contribution patterns.</p>
        </div>
        <div class="repo-grid repo-grid-trophies">
          {% include repository/repo_trophies.liquid username=user %}
        </div>
      </section>
    {% endfor %}
  {% endif %}
</div>
