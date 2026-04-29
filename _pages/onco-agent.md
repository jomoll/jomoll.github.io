---
layout: page
permalink: /onco-agent/
title: Agentic Clinical Reasoning over Longitudinal Myeloma Records
description: Agentic clinical reasoning over longitudinal myeloma records — a retrospective evaluation against expert consensus
nav: false
og_image: 
---

<style>
.page-header,
.post-header,
h1.post-title,
header.post-header {
    display: none !important;
}
</style>

<div class="container mt-5">
    <div class="row justify-content-center text-center">
        <div class="col-lg-12">
            <h1 class="mb-4">Agentic Clinical Reasoning over Longitudinal Myeloma Records: A Retrospective Evaluation against Expert Consensus</h1>
            <div class="mb-3">
                <a href="https://jomoll.github.io">Johannes Moll</a><sup>*,†1,2,3</sup>,
                Jannik Lübberstedt<sup>†2</sup>,
                Christoph Nuernbergk<sup>4</sup>,
                Jacob Stroh<sup>4</sup>,
                Luisa Mertens<sup>4</sup>,
                Anna Purcarea<sup>4</sup>,
                Christopher Zirn<sup>2</sup>,
                Zeineb Benchaaben<sup>2</sup>,
                Fabian Drexel<sup>1,2</sup>,
                Hartmut Häntze<sup>2,5</sup>,
                Anirudh Narayanan<sup>2,5</sup>,
                Friedrich Puttkammer<sup>2,5</sup>,
                Andrei Zhukov<sup>6</sup>,
                Jacqueline Lammert<sup>7,8</sup>,
                Sebastian Ziegelmayer<sup>2</sup>,
                Markus Graf<sup>2</sup>,
                Marion Högner<sup>4</sup>,
                Marcus Makowski<sup>2</sup>,
                Florian Bassermann<sup>4,9,10,11</sup>,
                <a href="https://scholar.google.com/citations?hl=de&user=n-AEUgsAAAAJ">Lisa C. Adams</a><sup>2</sup>,
                <a href="https://jiazhenpan.me">Jiazhen Pan</a><sup>1,12,13</sup>,
                <a href="https://scholar.google.com/citations?hl=de&user=H0O0WnQAAAAJ">Daniel Rueckert</a><sup>1,13,14</sup>,
                Krischan Braitsch<sup>‡4</sup>,
                and <a href="https://scholar.google.com/citations?hl=de&user=wIEgwbkAAAAJ">Keno K. Bressem</a><sup>‡2,3</sup>
            </div>
            <div class="mb-4">
                <small><sup>†</sup>Equal contribution &nbsp;|&nbsp; <sup>‡</sup>Equal senior contribution</small>
            </div>
            <!-- Publication Links -->
            <div class="mt-4 mb-4">
                <a href="https://arxiv.org/abs/2604.24473" target="_blank" class="btn btn-dark btn-lg rounded-pill me-2 mb-2">
                    <i class="ai ai-arxiv me-1"></i> arXiv
                </a>
                <a href="https://github.com/onco-agent/onco-agent" target="_blank" class="btn btn-dark btn-lg rounded-pill me-2 mb-2">
                    <i class="fab fa-github me-1"></i> Code
                </a>
            </div>
        </div>
    </div>
</div>

<div class="container mt-4">
    <div class="row justify-content-center">
        <div class="col-lg-12">
            <h2 class="text-center mb-4">Abstract</h2>
            <p class="text-justify">
                <strong>Background.</strong> Multiple myeloma is managed through sequential lines of therapy over years to decades, with each treatment decision depending on cumulative disease history distributed across dozens to hundreds of heterogeneous clinical documents. Whether large language model-based systems can synthesise this evidence at a level approaching expert agreement has not been established.
            </p>
            <p class="text-justify">
                <strong>Methods.</strong> A retrospective evaluation was conducted on longitudinal clinical records of 811 patients with multiple myeloma treated at a tertiary medical centre between 2001 and 2026, covering 44,962 documents and 1,334,677 laboratory values, with external validation on MIMIC-IV. An agentic reasoning system was compared against single-pass retrieval-augmented generation (RAG), iterative RAG, and full-context input on 469 patient–question pairs derived from 48 templates stratified into three complexity levels. The reference standard was established by independent double annotation from four oncologists with adjudication by a senior haematologist.
            </p>
            <p class="text-justify">
                <strong>Findings.</strong> Iterative retrieval-augmented generation and full-context input converged on a shared performance ceiling (75·4% versus 75·8%, Bonferroni-corrected <em>p</em> = 1·00). The agentic system reached 79·6% concordance (95% CI 76·4–82·8), significantly exceeding both baselines (+3·8 and +4·2 percentage points; <em>p</em> = 0·006 and 0·007). Gains increased with question complexity, reaching +9·4 percentage points on criteria-based synthesis (<em>p</em> = 0·032), and with record length, reaching +13·5 percentage points in the top decile (exploratory, <em>n</em> = 10). The system error rate (12·2%) was comparable to expert disagreement (13·6%), but severity distributions were inverted, with 57·8% of system errors classified as clinically significant against 18·8% of expert disagreements.
            </p>
            <p class="text-justify">
                <strong>Interpretation.</strong> Agentic reasoning was the only approach to exceed the shared performance ceiling, with gains concentrated on the most complex questions and longest records. The greater clinical consequence of residual system errors relative to expert disagreement indicates that prospective evaluation in routine care will be required before these findings translate into measurable patient benefit.
            </p>
            <p class="text-justify">
                <strong>Funding.</strong> Bayern Innovativ (Bavarian State Ministry of Economics), Grant Number: LSM-2403-0006.
            </p>
        </div>
    </div>
</div>

<div class="container mt-5">
    <div class="row justify-content-center">
        <div class="col-lg-12">
            <h2 class="text-center mb-4">Demo</h2>
            <div class="row">
                <div class="col-md-4 mb-3">
                    <video class="w-100" controls muted playsinline style="border-radius: 8px;">
                        <source src="{{ '/assets/video/example_1.mov' | relative_url }}" type="video/mp4">
                    </video>
                </div>
                <div class="col-md-4 mb-3">
                    <video class="w-100" controls muted playsinline style="border-radius: 8px;">
                        <source src="{{ '/assets/video/example_2.mov' | relative_url }}" type="video/mp4">
                    </video>
                </div>
                <div class="col-md-4 mb-3">
                    <video class="w-100" controls muted playsinline style="border-radius: 8px;">
                        <source src="{{ '/assets/video/example_3.mov' | relative_url }}" type="video/mp4">
                    </video>
                </div>
            </div>
        </div>
    </div>
</div>

<section class="section" id="BibTeX">
    <div class="container is-max-desktop content">
        <h2 class="title has-text-centered">BibTeX</h2>
        <div class="columns is-centered">
            <div class="column is-four-fifths">
                <pre><code>@article{moll2026agentic,
  title={Agentic clinical reasoning over longitudinal myeloma records: a retrospective evaluation against expert consensus},
  author={Moll, Johannes and L{\"u}bberstedt, Jannik and Nuernbergk, Christoph and Stroh, Jacob and Mertens, Luisa and Purcarea, Anna and Zirn, Christopher and Benchaaben, Zeineb and Drexel, Fabian and H{\"a}ntze, Hartmut and Narayanan, Anirudh and Puttkammer, Friedrich and Zhukov, Andrei and Lammert, Jacqueline and Ziegelmayer, Sebastian and Graf, Markus and H{\"o}gner, Marion and Makowski, Marcus and Bassermann, Florian and Adams, Lisa C and Pan, Jiazhen and Rueckert, Daniel and Braitsch, Krischan and Bressem, Keno K},
  journal={arXiv preprint arXiv:2604.24473},
  year={2026}
}</code></pre>
            </div>
        </div>
    </div>
</section>
