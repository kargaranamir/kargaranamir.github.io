---
layout: page
title: glotsuite
permalink: /glotsuite/
description: open tools, corpora and benchmarks for minority languages.
nav: true
nav_order: 3

glot:
  - name: GlotLID
    logo: glotlid.svg
    tagline: Language identification for 2,000+ labels
    about: An open-source fastText language identifier covering more than 2,000 labels, built for noisy web text and low-resource languages.
    paper: https://aclanthology.org/2023.findings-emnlp.410/
    venue: EMNLP 2023
    repo: cisnlp/GlotLID
    links:
      - { label: Demo, url: "https://huggingface.co/spaces/cis-lmu/glotlid-space" }
      - { label: Model, url: "https://huggingface.co/cis-lmu/glotlid" }
  - name: GlotScript
    logo: glotscript.svg
    tagline: Writing system identification
    about: A resource and tool for identifying writing systems (ISO 15924) for thousands of languages, and for checking which scripts a text is written in.
    paper: https://aclanthology.org/2024.lrec-main.687/
    venue: LREC-COLING 2024
    repo: cisnlp/GlotScript
  - name: GlotCC
    logo: glotcc.svg
    tagline: Open CommonCrawl corpus for 1,000+ languages
    about: A clean, document-level corpus built from CommonCrawl for more than 1,000 languages, together with the open pipeline that produced it.
    paper: https://arxiv.org/abs/2410.23825
    venue: NeurIPS 2024
    repo: cisnlp/GlotCC
    links:
      - { label: Data, url: "https://huggingface.co/datasets/cis-lmu/GlotCC-V1" }
  - name: GlotWeb
    logo: glotweb.svg
    tagline: Web indexing for 400+ minority languages
    about: A web index of verified pages in 400+ languages, many of them missing from major multilingual datasets, with an interactive search demo.
    paper: https://dl.acm.org/doi/10.1145/3774904.3792887
    venue: WWW 2026
    repo: cisnlp/GlotWeb
    links:
      - { label: Demo, url: "https://huggingface.co/spaces/cis-lmu/GlotWeb" }
  - name: GlotOCR Bench
    logo: glotocr-bench.svg
    tagline: OCR benchmark across 100+ Unicode scripts
    about: A benchmark showing that current OCR models, including frontier models, still struggle beyond a handful of Unicode scripts.
    paper: https://arxiv.org/abs/2604.12978
    venue: arXiv 2026
    repo: cisnlp/glotocr-bench
    links:
      - { label: Data, url: "https://huggingface.co/datasets/cis-lmu/GlotOCR-bench" }
  - name: GlotStoryBook
    logo: glotstorybook.svg
    tagline: Children's storybooks in 180 languages
    about: A parallel collection of children's storybooks in 180 languages, useful for evaluation and for training in truly low-resource settings.
    repo: cisnlp/GlotStoryBook
    links:
      - { label: Data, url: "https://huggingface.co/datasets/cis-lmu/GlotStoryBook" }
  - name: GlotSparse
    logo: glotsparse.svg
    tagline: News corpora for under-resourced languages
    about: Collected news text for languages with very little data available online.
    links:
      - { label: Data, url: "https://huggingface.co/datasets/cis-lmu/GlotSparse" }
---

<style>
  .glot-hero { text-align: center; margin: 0.5rem 0 1.5rem; }
  .glot-hero img { width: min(300px, 70%); height: auto; }
  .glot-hero p { max-width: 36rem; margin: 0.75rem auto 0; color: var(--global-text-color-light); }
  .glot-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 1.25rem; margin: 1rem 0 2rem; }
  .glot-card {
    display: flex; flex-direction: column; border: 1px solid var(--global-divider-color); border-radius: 14px;
    background: var(--global-card-bg-color); padding: 1rem 1rem 0.9rem; transition: transform 0.15s ease, box-shadow 0.15s ease;
  }
  .glot-card:hover { transform: translateY(-3px); box-shadow: 0 6px 18px rgba(0, 0, 0, 0.08); }
  .glot-card .glot-logo { background: #fff; border-radius: 10px; padding: 0.6rem; text-align: center; }
  .glot-card .glot-logo img { width: 100%; max-width: 200px; height: 150px; object-fit: contain; }
  .glot-card h3 { font-size: 1.1rem; margin: 0.8rem 0 0.15rem; font-weight: 600; }
  .glot-card .glot-tag { font-size: 0.85rem; color: var(--global-theme-color); margin-bottom: 0.4rem; }
  .glot-card .glot-about { font-size: 0.88rem; flex-grow: 1; margin-bottom: 0.7rem; }
  .glot-card .glot-links { display: flex; flex-wrap: wrap; gap: 0.35rem; align-items: center; }
  .glot-card .glot-links a {
    font-size: 0.75rem; border: 1px solid var(--global-theme-color); color: var(--global-theme-color); border-radius: 999px;
    padding: 0.1rem 0.6rem; text-decoration: none;
  }
  .glot-card .glot-links a:hover { background: var(--global-theme-color); color: #fff; }
  .glot-card .glot-stars { margin-top: 0.55rem; height: 20px; }
</style>

<div class="glot-hero">
  <img src="{{ '/assets/img/glot/glotsuite.svg' | relative_url }}" alt="GlotSuite logo">
  <p>GlotSuite is the family of open tools, corpora and benchmarks I work on for low-resource and minority languages, from identifying the language and script of a text to collecting, indexing and evaluating data for them.</p>
</div>

<div class="glot-grid">
{% for g in page.glot %}
  <div class="glot-card">
    <div class="glot-logo"><img src="{{ '/assets/img/glot/' | append: g.logo | relative_url }}" alt="{{ g.name }} logo" loading="lazy"></div>
    <h3>{{ g.name }}</h3>
    <div class="glot-tag">{{ g.tagline }}</div>
    <div class="glot-about">{{ g.about }}</div>
    <div class="glot-links">
      {% if g.paper %}<a href="{{ g.paper }}">Paper · {{ g.venue }}</a>{% endif %}
      {% if g.repo %}<a href="https://github.com/{{ g.repo }}">Code</a>{% endif %}
      {% for l in g.links %}<a href="{{ l.url }}">{{ l.label }}</a>{% endfor %}
    </div>
    {% if g.repo %}
      <a class="glot-stars" href="https://github.com/{{ g.repo }}"><img src="https://img.shields.io/github/stars/{{ g.repo }}?style=social" alt="GitHub stars for {{ g.repo }}" loading="lazy"></a>
    {% endif %}
  </div>
{% endfor %}
</div>

Related work built on or around the suite: [Glot500](https://aclanthology.org/2023.acl-long.61/) (a language model for 500+ languages), [MaskLID](https://aclanthology.org/2024.acl-short.43/) (code-switching language identification with GlotLID) and [FineWeb2](https://arxiv.org/abs/2506.20920) (which uses GlotLID for language identification). All publications are on the [publications]({{ '/publications/' | relative_url }}) page.
