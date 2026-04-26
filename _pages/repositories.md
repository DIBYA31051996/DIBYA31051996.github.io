---
layout: page
permalink: /repositories/
title: Repositories
description: Code, tools, and research repositories.
nav: true
nav_order: 6
---

{% assign gh_user = site.data.repositories.github_users.first %}

<style>
  .post-header .post-description,
  .post-header .desc {
    display: none !important;
  }

  .repo-shell {
    max-width: 1180px;
    margin: 0 auto;
    display: grid;
    gap: 1.15rem;
  }

  .repo-overview {
    display: grid;
    grid-template-columns: 320px minmax(0, 1fr);
    gap: 1rem;
  }

  .repo-card {
    border: 1px solid rgba(175, 194, 235, 0.16);
    border-radius: 22px;
    background:
      radial-gradient(circle at top right, rgba(90, 141, 255, 0.12), transparent 36%),
      linear-gradient(180deg, rgba(13, 20, 38, 0.95), rgba(8, 14, 28, 0.98));
    box-shadow:
      0 18px 40px rgba(0, 0, 0, 0.24),
      inset 0 1px 0 rgba(255, 255, 255, 0.04);
  }

  .repo-profile {
    padding: 1.2rem;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .repo-avatar-wrap {
    position: relative;
    width: 118px;
    height: 118px;
  }

  .repo-avatar-wrap::after {
    content: "";
    position: absolute;
    inset: -8px;
    border-radius: 32px;
    background: linear-gradient(135deg, rgba(74, 185, 255, 0.22), rgba(121, 92, 255, 0.2));
    z-index: 0;
    filter: blur(2px);
  }

  .repo-avatar {
    position: relative;
    z-index: 1;
    width: 118px;
    height: 118px;
    border-radius: 28px;
    object-fit: cover;
    display: block;
    border: 1px solid rgba(190, 207, 255, 0.24);
    box-shadow: 0 18px 34px rgba(0, 0, 0, 0.24);
  }

  .repo-profile-copy h1,
  .repo-panel-heading h2,
  .repo-hero-copy h2,
  .repo-pinned-card h3 {
    color: #f8fbff;
    font-weight: 800;
  }

  .repo-profile-copy h1 {
    margin: 0 0 0.3rem;
    font-size: clamp(1.95rem, 3vw, 2.4rem);
    line-height: 1.05;
  }

  .repo-handle {
    color: #8cc7ff;
    font-size: 1rem;
    font-weight: 700;
    margin-bottom: 0.65rem;
  }

  .repo-profile-copy p,
  .repo-hero-copy p,
  .repo-panel-heading p,
  .repo-pinned-card p,
  .repo-mini-card span {
    color: #c6d4f2;
    line-height: 1.6;
  }

  .repo-status {
    display: inline-flex;
    align-items: center;
    gap: 0.48rem;
    width: fit-content;
    padding: 0.5rem 0.9rem;
    border-radius: 999px;
    border: 1px solid rgba(178, 200, 255, 0.18);
    background: rgba(255, 255, 255, 0.04);
    color: #edf4ff;
    font-weight: 700;
  }

  .repo-status::before {
    content: "";
    width: 10px;
    height: 10px;
    border-radius: 999px;
    background: linear-gradient(135deg, #7be0ff, #7f5cff);
    box-shadow:
      0 0 0 3px rgba(123, 224, 255, 0.12),
      0 0 14px rgba(127, 92, 255, 0.26);
  }

  .repo-profile-meta {
    display: grid;
    gap: 0.75rem;
  }

  .repo-mini-card {
    padding: 0.9rem 0.95rem;
    border-radius: 16px;
    border: 1px solid rgba(175, 194, 235, 0.14);
    background: rgba(255, 255, 255, 0.035);
  }

  .repo-mini-card strong {
    display: block;
    margin-bottom: 0.2rem;
    color: #ffffff;
    font-size: 1.15rem;
    font-weight: 800;
  }

  .repo-main {
    padding: 1.2rem;
    display: grid;
    gap: 1rem;
  }

  .repo-hero {
    padding: 0.25rem 0 0.2rem;
  }

  .repo-pill {
    display: inline-flex;
    align-items: center;
    gap: 0.45rem;
    padding: 0.5rem 0.88rem;
    border-radius: 999px;
    border: 1px solid rgba(156, 181, 238, 0.24);
    background: linear-gradient(135deg, rgba(54, 175, 192, 0.18), rgba(99, 88, 212, 0.18));
    color: #edf4ff;
    font-size: 0.9rem;
    font-weight: 800;
  }

  .repo-hero-copy h2 {
    margin: 0.8rem 0 0.55rem;
    font-size: clamp(2rem, 4vw, 3rem);
    line-height: 1.02;
  }

  .repo-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 0.7rem;
    margin-top: 1rem;
  }

  .repo-link-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    border-radius: 999px;
    padding: 0.76rem 1.08rem;
    text-decoration: none;
    font-weight: 700;
    color: #ffffff;
    background: linear-gradient(90deg, #2eaed6, #5974ff);
    border: 1px solid transparent;
    transition: transform 0.2s ease, filter 0.2s ease, border-color 0.2s ease;
  }

  .repo-link-btn:hover {
    transform: translateY(-1px);
    filter: brightness(1.06);
    color: #ffffff;
    text-decoration: none;
  }

  .repo-link-btn-soft {
    color: #eaf1ff;
    background: rgba(29, 44, 78, 0.82);
    border-color: rgba(166, 192, 255, 0.26);
  }

  .repo-metrics {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 0.85rem;
  }

  .repo-metric-card {
    padding: 1rem;
    border-radius: 18px;
    border: 1px solid rgba(175, 194, 235, 0.14);
    background: rgba(255, 255, 255, 0.035);
  }

  .repo-metric-card strong {
    display: block;
    color: #ffffff;
    font-size: 1.6rem;
    line-height: 1;
    margin-bottom: 0.35rem;
  }

  .repo-metric-card span {
    color: #c6d4f2;
    font-weight: 600;
  }

  .repo-focus-grid,
  .repo-pinned-grid {
    display: grid;
    gap: 1rem;
  }

  .repo-focus-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .repo-panel-block {
    padding: 1.15rem;
  }

  .repo-panel-heading {
    margin-bottom: 0.9rem;
  }

  .repo-panel-heading h2 {
    margin: 0 0 0.3rem;
    font-size: 1.55rem;
  }

  .repo-focus-card {
    padding: 1rem;
    border-radius: 18px;
    border: 1px solid rgba(175, 194, 235, 0.14);
    background:
      linear-gradient(180deg, rgba(16, 24, 43, 0.92), rgba(10, 17, 31, 0.96)),
      radial-gradient(circle at top right, rgba(96, 143, 255, 0.12), transparent 40%);
  }

  .repo-focus-card h3 {
    margin: 0 0 0.6rem;
    color: #f8fbff;
    font-size: 1.2rem;
    font-weight: 800;
  }

  .repo-tag-row {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-top: 0.8rem;
  }

  .repo-tag-row span {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    border-radius: 999px;
    padding: 0.28rem 0.7rem;
    font-size: 0.78rem;
    font-weight: 700;
    color: #e7f0ff;
    background: rgba(45, 63, 104, 0.72);
    border: 1px solid rgba(166, 192, 255, 0.18);
  }

  .repo-pinned-grid {
    grid-template-columns: repeat(3, minmax(0, 1fr));
  }

  .repo-pinned-card {
    padding: 1.05rem;
    border-radius: 20px;
    border: 1px solid rgba(175, 194, 235, 0.16);
    background:
      linear-gradient(180deg, rgba(14, 23, 43, 0.92), rgba(10, 17, 33, 0.96)),
      radial-gradient(circle at top right, rgba(96, 143, 255, 0.14), transparent 40%);
    box-shadow:
      0 14px 32px rgba(0, 0, 0, 0.18),
      inset 0 1px 0 rgba(255, 255, 255, 0.04);
  }

  .repo-pinned-type {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    border-radius: 999px;
    padding: 0.32rem 0.72rem;
    margin-bottom: 0.75rem;
    font-size: 0.8rem;
    font-weight: 800;
    color: #f4f8ff;
    background: linear-gradient(135deg, rgba(63, 118, 212, 0.42), rgba(113, 81, 215, 0.34));
    border: 1px solid rgba(166, 192, 255, 0.24);
  }

  .repo-pinned-card h3 {
    margin: 0 0 0.28rem;
    font-size: 1.34rem;
  }

  .repo-slug {
    font-size: 0.92rem;
    color: #90b8ff;
    margin-bottom: 0.75rem;
  }

  .repo-summary {
    min-height: 78px;
    margin-bottom: 0.9rem;
  }

  .repo-actions-row {
    display: flex;
    flex-wrap: wrap;
    gap: 0.65rem;
  }

  @media (max-width: 980px) {
    .repo-overview,
    .repo-focus-grid,
    .repo-pinned-grid,
    .repo-metrics {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="repo-shell">
  <section class="repo-overview">
    <aside class="repo-card repo-profile">
      <div class="repo-avatar-wrap">
        <img class="repo-avatar" src="https://github.com/{{ gh_user }}.png" alt="{{ gh_user }} GitHub avatar">
      </div>

      <div class="repo-profile-copy">
        <h1>Dibya Kirti Mishra</h1>
        <div class="repo-handle">@{{ gh_user }}</div>
        <p>
          Solar-physics code, data products, and website work collected into one GitHub-facing profile overview.
          The focus stays on research tools, long-term solar variability, and reusable analysis workflows.
        </p>
      </div>

      <div class="repo-status">Public research code overview</div>

      <div class="repo-profile-meta">
        <div class="repo-mini-card">
          <strong>Primary themes</strong>
          <span>Solar cycle, magnetic diagnostics, long-baseline data, and analysis workflows.</span>
        </div>
        <div class="repo-mini-card">
          <strong>Profile link</strong>
          <span><a href="https://github.com/{{ gh_user }}" target="_blank" rel="noopener">@{{ gh_user }}</a></span>
        </div>
      </div>
    </aside>

    <div class="repo-card repo-main">
      <section class="repo-hero">
        <div class="repo-hero-copy">
          <div class="repo-pill">GitHub Overview</div>
          <h2>Research code, project pages, and analysis repositories in one place.</h2>
          <p>
            This page mirrors the feel of a polished GitHub profile overview: a concise identity block, pinned
            repositories, and a quick sense of what kinds of tools and data-oriented work live in the account.
          </p>

          <div class="repo-actions">
            <a class="repo-link-btn" href="https://github.com/{{ gh_user }}" target="_blank" rel="noopener">Open GitHub profile</a>
            <a class="repo-link-btn repo-link-btn-soft" href="https://github.com/{{ gh_user }}?tab=repositories" target="_blank" rel="noopener">Browse repositories</a>
          </div>
        </div>
      </section>

      <section class="repo-metrics">
        <div class="repo-metric-card">
          <strong>{{ site.data.repositories.github_repos.size }}</strong>
          <span>Pinned repositories</span>
        </div>
        <div class="repo-metric-card">
          <strong>3</strong>
          <span>Core work modes: software, data, website</span>
        </div>
        <div class="repo-metric-card">
          <strong>1</strong>
          <span>Public profile entry point</span>
        </div>
      </section>
    </div>
  </section>

  <section class="repo-card repo-panel-block">
    <div class="repo-panel-heading">
      <h2>Overview</h2>
      <p>A quick profile-style snapshot of what the GitHub account is centered on.</p>
    </div>

    <div class="repo-focus-grid">
      <article class="repo-focus-card">
        <h3>What shows up here</h3>
        <p>
          Repositories are organized around solar data handling, archive-friendly project material, and the structure
          of this personal research website.
        </p>
        <div class="repo-tag-row">
          <span>Solar physics</span>
          <span>Data products</span>
          <span>Research tools</span>
        </div>
      </article>

      <article class="repo-focus-card">
        <h3>How the profile reads</h3>
        <p>
          The account works best as a clean public overview: a small set of pinned repositories, direct GitHub access,
          and enough context to understand the purpose of each project quickly.
        </p>
        <div class="repo-tag-row">
          <span>Public profile</span>
          <span>Pinned work</span>
          <span>Readable overview</span>
        </div>
      </article>
    </div>
  </section>

  {% if site.data.repositories.github_repos %}
    <section class="repo-card repo-panel-block">
      <div class="repo-panel-heading">
        <h2>Pinned repositories</h2>
        <p>Selected repositories presented more like a GitHub profile overview than a plain list.</p>
      </div>

      <div class="repo-pinned-grid">
        {% for repo in site.data.repositories.github_repos %}
          {% assign repo_parts = repo | split: '/' %}
          {% assign repo_name = repo_parts[1] %}
          <article class="repo-pinned-card">
            <div class="repo-pinned-type">
              {% case repo_name %}
                {% when 'scoobi' %}Software
                {% when 'kosopni' %}Dataset
                {% else %}Website
              {% endcase %}
            </div>

            <h3>{{ repo_name }}</h3>
            <div class="repo-slug">{{ repo }}</div>

            <p class="repo-summary">
              {% case repo_name %}
                {% when 'scoobi' %}
                  Solar analysis utilities and workflow-friendly code for working with observational products and repeatable research steps.
                {% when 'kosopni' %}
                  Repository associated with long-baseline polar network index material and supporting solar-cycle data context.
                {% else %}
                  Personal website source code covering page structure, styling, content organization, and visual presentation.
              {% endcase %}
            </p>

            <div class="repo-tag-row">
              {% case repo_name %}
                {% when 'scoobi' %}
                  <span>Python</span><span>Workflows</span><span>Solar tools</span>
                {% when 'kosopni' %}
                  <span>Archive</span><span>Solar cycle</span><span>Data</span>
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
