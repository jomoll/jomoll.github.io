---
layout: page
permalink: /onco-agent/
title: Skill-Guided Agentic Reasoning for Longitudinal Myeloma Records
description: Skill-guided agentic reasoning enables longitudinal synthesis of myeloma records at expert-level concordance (npj Precision Oncology, 2026)
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
            <h1 class="mb-4">Skill-Guided Agentic Reasoning Enables Longitudinal Synthesis of Myeloma Records at Expert-Level Concordance</h1>
            <h5 class="mb-4 text-muted">npj Precision Oncology, 2026</h5>
            <div class="mb-3">
                <span style="white-space:nowrap"><a href="https://jomoll.github.io">Johannes Moll</a><sup>*,†1,2,3</sup></span>,
                <span style="white-space:nowrap">Jannik Lübberstedt<sup>†2</sup></span>,
                <span style="white-space:nowrap">Christoph Nuernbergk<sup>4</sup></span>,
                <span style="white-space:nowrap">Jacob Stroh<sup>4</sup></span>,
                <span style="white-space:nowrap">Luisa Mertens<sup>4</sup></span>,
                <span style="white-space:nowrap">Anna Purcarea<sup>4</sup></span>,
                <span style="white-space:nowrap">Christopher Zirn<sup>2</sup></span>,
                <span style="white-space:nowrap">Zeineb Benchaaben<sup>2</sup></span>,
                <span style="white-space:nowrap">Fabian Drexel<sup>1,2</sup></span>,
                <span style="white-space:nowrap">Hartmut Häntze<sup>2,5</sup></span>,
                <span style="white-space:nowrap">Anirudh Narayanan<sup>2,5</sup></span>,
                <span style="white-space:nowrap">Friedrich Puttkammer<sup>2,5</sup></span>,
                <span style="white-space:nowrap">Andrei Zhukov<sup>6</sup></span>,
                <span style="white-space:nowrap">Jacqueline Lammert<sup>7,8</sup></span>,
                <span style="white-space:nowrap">Sebastian Ziegelmayer<sup>2</sup></span>,
                <span style="white-space:nowrap">Markus Graf<sup>2</sup></span>,
                <span style="white-space:nowrap">Marion Högner<sup>4</sup></span>,
                <span style="white-space:nowrap">Marcus Makowski<sup>2</sup></span>,
                <span style="white-space:nowrap">Florian Bassermann<sup>4,9,10,11</sup></span>,
                <span style="white-space:nowrap"><a href="https://scholar.google.com/citations?hl=de&user=n-AEUgsAAAAJ">Lisa C. Adams</a><sup>2</sup></span>,
                <span style="white-space:nowrap"><a href="https://jiazhenpan.me">Jiazhen Pan</a><sup>1,12,13</sup></span>,
                <span style="white-space:nowrap"><a href="https://scholar.google.com/citations?hl=de&user=H0O0WnQAAAAJ">Daniel Rueckert</a><sup>1,13,14</sup></span>,
                <span style="white-space:nowrap"><a href="https://med3.mri.tum.de/de/die-klinik/team">Krischan Braitsch</a><sup>‡4</sup></span>,
                and <span style="white-space:nowrap"><a href="https://scholar.google.com/citations?hl=de&user=wIEgwbkAAAAJ">Keno K. Bressem</a><sup>‡2,3</sup></span>
            </div>
            <div class="mb-4">
                <small><sup>†</sup>Equal contribution &nbsp;|&nbsp; <sup>‡</sup>Equal senior contribution</small>
            </div>
            <!-- Publication Links -->
            <div class="mt-4 mb-4">
                <a href="https://www.nature.com/articles/s41698-026-01733-2" target="_blank" class="btn btn-dark btn-lg rounded-pill me-2 mb-2">
                    <i class="fas fa-file-pdf me-1"></i> Paper
                </a>
                <a href="https://arxiv.org/abs/2604.24473" target="_blank" class="btn btn-dark btn-lg rounded-pill me-2 mb-2">
                    <i class="ai ai-arxiv me-1"></i> arXiv
                </a>
                <a href="https://github.com/jomoll/onco-agent" target="_blank" class="btn btn-dark btn-lg rounded-pill me-2 mb-2">
                    <i class="fab fa-github me-1"></i> Code
                </a>
            </div>
        </div>
    </div>
</div>


<div class="container mt-4">
    <div class="row justify-content-center">
        <div class="col-lg-12">
            <h2 class="text-center mb-4">About</h2>
            <p>Onco-Agent is a multi-turn retrieval-augmented agent for answering structured clinical questions from patient records. It is the system described in our paper: <a href="https://www.nature.com/articles/s41698-026-01733-2">Skill-guided agentic reasoning enables longitudinal synthesis of myeloma records at expert-level concordance</a> (<em>npj Precision Oncology</em>, 2026).</p>
            <p>Given a patient's clinical record (discharge letters, radiology reports, lab values, etc.) and a doctor's question, the agent:</p>
            <ol>
                <li><strong>Plans</strong> which information to retrieve and which domain skills to apply.</li>
                <li><strong>Retrieves</strong> relevant report sections and lab values using specialized retrieval tools with date and type filters.</li>
                <li><strong>Applies</strong> domain-specific skills (clinical workflows, evidence ranking, scoring systems).</li>
                <li><strong>Produces</strong> a structured answer with inline citations.</li>
            </ol>
        </div>
    </div>
</div>

<div class="container mt-5">
    <div class="row justify-content-center">
        <div class="col-lg-12">
            <h2 class="text-center mb-4">Demo</h2>
            <table style="width:100%; table-layout:fixed;">
                <tr>
                    <td align="center" style="width:33%; padding: 0 8px;">
                        <video controls muted playsinline style="width:100%; border-radius:8px;">
                            <source src="{{ '/assets/video/example_1.mov' | relative_url }}" type="video/mp4">
                        </video>
                        <br>Single-document lookup
                    </td>
                    <td align="center" style="width:33%; padding: 0 8px;">
                        <video controls muted playsinline style="width:100%; border-radius:8px;">
                            <source src="{{ '/assets/video/example_2.mov' | relative_url }}" type="video/mp4">
                        </video>
                        <br>Temporal reasoning
                    </td>
                    <td align="center" style="width:33%; padding: 0 8px;">
                        <video controls muted playsinline style="width:100%; border-radius:8px;">
                            <source src="{{ '/assets/video/example_3.mov' | relative_url }}" type="video/mp4">
                        </video>
                        <br>Multi-criteria synthesis
                    </td>
                </tr>
            </table>
        </div>
    </div>
</div>

<div class="container mt-4">
    <div class="row justify-content-center">
        <div class="col-lg-12">
            <h2 class="text-center mb-4">Abstract</h2>
            <p class="text-justify">
                Patients with multiple myeloma accumulate hundreds of clinical documents over years of sequential therapy, and every treatment decision depends on synthesis across that history. Whether large language model–based systems can match expert agreement on this task, and where they fail, has not been established. On longitudinal records of 811 patients treated over 25 years (44,962 documents and 1,334,677 laboratory values), an agentic reasoning system guided by an indexed clinical skill library was compared against single-pass retrieval-augmented generation (RAG), iterative RAG, iterative RAG augmented with the same skill library, and full-context input on 469 expert-adjudicated patient-question pairs, with an exploratory cross-dataset evaluation on MIMIC-IV. The skill-guided agent exceeded the ceiling at which iterative RAG (75.7%) and full-context input (75.8%) converged, reaching 80.1% concordance, with its advantage widening on the most complex tasks (+11.2 percentage points) and longest records. Providing the same skill library to iterative RAG matched the agent in aggregate (79.0%) and on shorter records, whereas the agent retained a significant advantage on the longest records (+10.3 percentage points in the top decile, <em>p</em> = 0.017) and a numerical, non-significant advantage on the most complex questions (+5.4 percentage points). The aggregate error rate (12.2%) was comparable to expert disagreement (13.6%), but a higher proportion of system errors were clinically significant (57.8 versus 18.8%).
            </p>
        </div>
    </div>
</div>
<section class="section" id="BibTeX">
    <div class="container is-max-desktop content">
        <h2 class="title has-text-centered">BibTeX</h2>
        <div class="columns is-centered">
            <div class="column is-four-fifths">
                <pre><code>@article{moll2026agentic,
  title   = {Skill-guided agentic reasoning enables longitudinal synthesis of myeloma records at expert-level concordance},
  author  = {Moll, Johannes and L{\"u}bberstedt, Jannik and Nuernbergk, Christoph and Stroh, Jacob and Mertens, Luisa and Purcarea, Anna and Zirn, Christopher and Benchaaben, Zeineb and Drexel, Fabian and H{\"a}ntze, Hartmut and Narayanan, Anirudh and Puttkammer, Friedrich and Zhukov, Andrei and Lammert, Jacqueline and Ziegelmayer, Sebastian and Graf, Markus and H{\"o}gner, Marion and Makowski, Marcus and Bassermann, Florian and Adams, Lisa C. and Pan, Jiazhen and Rueckert, Daniel and Braitsch, Krischan and Bressem, Keno K.},
  journal = {npj Precision Oncology},
  volume  = {10},
  number  = {1},
  pages   = {389},
  year    = {2026},
  doi     = {10.1038/s41698-026-01733-2}
}</code></pre>
            </div>
        </div>
    </div>
</section>
