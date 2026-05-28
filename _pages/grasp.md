---
layout: page
permalink: /grasp/
title: "GRASP: Gated Regression-Aware Skill Proposer for Self-Improving LLM Agents"
description: 
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

/* Skill browser */
.skill-card {
  border: none;
  border-radius: 12px;
  box-shadow: 0 2px 12px rgba(0,0,0,0.08);
}
.skill-card .card-header {
  border-radius: 12px 12px 0 0 !important;
  background: #f8f9fa;
  border-bottom: 1px solid #e9ecef;
}
.domain-badge { font-size: 0.78rem; padding: 0.35em 0.65em; border-radius: 6px; font-weight: 600; }
.domain-badge.clinical       { background: #dbeafe; color: #1d4ed8; }
.domain-badge.clinical-v2    { background: #ede9fe; color: #6d28d9; }
.domain-badge.alfworld        { background: #dcfce7; color: #15803d; }
.domain-badge.webshop         { background: #ffedd5; color: #c2410c; }
.domain-badge.dbbench         { background: #fef9c3; color: #854d0e; }
.domain-badge.os              { background: #fee2e2; color: #b91c1c; }

.model-pill {
  font-size: 0.72rem;
  padding: 0.2em 0.55em;
  border-radius: 20px;
  background: #e9ecef;
  color: #495057;
  font-weight: 500;
}
.skill-title { font-size: 1.3rem; font-weight: 700; line-height: 1.3; }
.skill-desc  { color: #495057; font-size: 0.95rem; }
.tag-pill {
  font-size: 0.72rem;
  padding: 0.2em 0.55em;
  border-radius: 20px;
  background: #f1f3f5;
  color: #495057;
  border: 1px solid #dee2e6;
}
.prov-stat { text-align: center; }
.prov-stat .val { font-size: 1.35rem; font-weight: 700; line-height: 1; }
.prov-stat .lbl { font-size: 0.72rem; color: #6c757d; margin-top: 2px; }
.prov-stat.fixes .val    { color: #15803d; }
.prov-stat.regress .val  { color: #b91c1c; }
.prov-stat.score .val    { color: #1d4ed8; }

.filter-btn {
  border-radius: 20px;
  font-size: 0.82rem;
  padding: 0.3em 0.85em;
  border: 1.5px solid #dee2e6;
  background: white;
  color: #495057;
  transition: all 0.15s;
}
.filter-btn:hover, .filter-btn.active {
  background: #212529;
  color: white;
  border-color: #212529;
}
.skill-content-area {
  background: #f8f9fa;
  border-radius: 8px;
  padding: 1.2rem 1.4rem;
  font-size: 0.83rem;
  line-height: 1.65;
  max-height: 500px;
  overflow-y: auto;
  font-family: inherit;
  white-space: pre-wrap;
  word-break: break-word;
}
.skill-content-area h5 { font-size: 0.9rem; font-weight: 700; margin-top: 1em; margin-bottom: 0.3em; }
.skill-content-area code {
  background: #e9ecef;
  padding: 0.1em 0.3em;
  border-radius: 3px;
  font-size: 0.85em;
}
.skill-content-area pre {
  background: #212529;
  color: #f8f9fa;
  border-radius: 6px;
  padding: 0.75rem 1rem;
  font-size: 0.8rem;
  overflow-x: auto;
  white-space: pre;
}
.nav-btn {
  border-radius: 8px;
  padding: 0.45em 1.1em;
  font-weight: 500;
}
#skill-counter { font-size: 0.9rem; color: #6c757d; min-width: 70px; text-align: center; }
.action-badge-ADD    { background: #d1fae5; color: #065f46; }
.action-badge-MODIFY { background: #fef3c7; color: #92400e; }
.action-badge-REMOVE { background: #fee2e2; color: #7f1d1d; }

/* Results tables */
.results-table th { background: #212529; color: white; font-weight: 600; font-size: 0.85rem; }
.results-table td { font-size: 0.85rem; vertical-align: middle; }
.results-table .best { font-weight: 700; color: #15803d; }
.results-table .grasp-row { background: #f0fdf4; }
.section-divider { border: none; border-top: 2px solid #e9ecef; margin: 3rem 0; }
</style>

<!-- ============================================================ HERO -->
<div class="container mt-5">
  <div class="row justify-content-center text-center">
    <div class="col-lg-10">
      <h1 class="mb-4">GRASP: Gated Regression-Aware Skill Proposer<br>for Self-Improving LLM Agents</h1>
      <div class="mb-3" style="font-size:1rem; line-height:2">
        <span style="white-space:nowrap"><a href="https://jomoll.github.io">Johannes Moll</a><sup>1</sup></span>,
        <span style="white-space:nowrap">Jean-Philippe Corbeil<sup>2</sup></span>,
        <span style="white-space:nowrap"><a href="https://jiazhenpan.me">Jiazhen Pan</a><sup>1</sup></span>,
        <span style="white-space:nowrap">Martin Hadamitzky<sup>1</sup></span>,
        <span style="white-space:nowrap"><a href="https://scholar.google.com/citations?hl=de&user=H0O0WnQAAAAJ">Daniel Rueckert</a><sup>1</sup></span>,
        <span style="white-space:nowrap"><a href="https://scholar.google.com/citations?hl=de&user=n-AEUgsAAAAJ">Lisa Adams</a><sup>1,†</sup></span>,
        <span style="white-space:nowrap"><a href="https://scholar.google.com/citations?hl=de&user=wIEgwbkAAAAJ">Keno Bressem</a><sup>1,†</sup></span>
      </div>
      <div class="mb-3 text-muted" style="font-size:0.9rem">
        <sup>1</sup>Technical University of Munich &amp; TUM University Hospital &nbsp;|&nbsp;
        <sup>2</sup>Microsoft Healthcare &amp; Life Sciences
        <br><sup>†</sup>Equal senior authorship
      </div>
      <div class="mb-4">
        <span class="badge rounded-pill px-3 py-2" style="background:#212529; color:white; font-size:0.9rem;">EMNLP 2026</span>
      </div>
      <div class="mt-2 mb-4">
        <a href="{{ '/assets/pdf/EMNLP2026.pdf' | relative_url }}" target="_blank" class="btn btn-dark btn-lg rounded-pill me-2 mb-2">
          <i class="ai ai-arxiv me-1"></i> Paper
        </a>
        <a href="https://github.com/jomoll/GRASP" target="_blank" class="btn btn-dark btn-lg rounded-pill me-2 mb-2">
          <i class="fab fa-github me-1"></i> Code
        </a>
        <a href="https://pypi.org/project/grasp-skills/" target="_blank" class="btn btn-dark btn-lg rounded-pill me-2 mb-2">
          <i class="fab fa-python me-1"></i> PyPI
        </a>
      </div>
    </div>
  </div>
</div>

<!-- Banner -->
<div class="container mb-5">
  <div class="row justify-content-center">
    <div class="col-lg-11">
      <img src="https://raw.githubusercontent.com/jomoll/GRASP/main/assets/grasp_banner.png"
           alt="GRASP banner" style="width:100%; border-radius:10px;">
    </div>
  </div>
</div>

<!-- ============================================================ ABSTRACT -->
<div class="container mt-4">
  <div class="row justify-content-center">
    <div class="col-lg-10">
      <h2 class="text-center mb-4">Abstract</h2>
      <p class="text-justify">
        LLM agents acting in structured environments fail in operational rather than conversational ways, and reliability depends on procedural knowledge of the environment. Prior self-improvement methods accumulate natural-language guidance without checking that each new item preserves previously correct behavior, so a note that fixes one trajectory can silently regress another. We introduce <strong>GRASP</strong> (Gated Regression-Aware Skill Proposer), which treats agent improvement as a sequence of edits to a bounded skill library, admitting each candidate only if it produces a net improvement on a balanced held-out probe under a hard regression budget.
      </p>
      <p class="text-justify">
        We evaluate GRASP across five base models (gpt-oss-120b, DeepSeek V4 Flash, Gemini 3.1 Flash Lite, GPT-4.1, GPT-5.4) on two FHIR-based clinical benchmarks. On MedAgentBench, GRASP lifts gpt-oss-120b from 40.6% to 88.8%, exceeds the strongest of five self-improvement baselines by 21.0 points, and improves every other base model by 17.2 to 40.3 points. Ablations attribute the gain to comparative proposal generation, the acceptance gate, and the hard regression budget rather than to skill writing itself, which without validation is no better than using no skills. The mechanism generalizes beyond the clinical domain, improving agents on three of four non-clinical environments, and frozen libraries transfer across models — skills from a stronger model improve weaker executors beyond what they learn for themselves while the reverse does not, an asymmetry that no ungated baseline reproduces.
      </p>
    </div>
  </div>
</div>

<hr class="section-divider">

<!-- ============================================================ METHOD -->
<div class="container">
  <div class="row justify-content-center">
    <div class="col-lg-10">
      <h2 class="text-center mb-4">How GRASP Works</h2>
      <p>
        GRASP maintains a small, versioned library of behavioral <em>skills</em> — short Markdown documents injected into the agent's context at inference. After each batch of episodes, it proposes edits to that library and admits them only if they pass a regression-aware probe.
      </p>

      <div class="row g-3 mb-4">
        <div class="col-md-6 col-lg-4">
          <div class="p-3 rounded-3 h-100" style="background:#f8f9fa; border-left: 4px solid #0d6efd;">
            <div class="fw-bold mb-1">① Rollout &amp; Score</div>
            <div class="text-muted" style="font-size:0.9rem">Run the skill-aware agent on each dev sample and score it. Failed traces carry mechanism-specific labels (e.g., <code>date_filter_omitted</code>).</div>
          </div>
        </div>
        <div class="col-md-6 col-lg-4">
          <div class="p-3 rounded-3 h-100" style="background:#f8f9fa; border-left: 4px solid #6610f2;">
            <div class="fw-bold mb-1">② Propose</div>
            <div class="text-muted" style="font-size:0.9rem">Group failures by mechanism label. For each group, a skill-writer LLM proposes <em>K</em> candidate edits — <strong>ADD</strong>, <strong>MODIFY</strong>, or <strong>REMOVE</strong>.</div>
          </div>
        </div>
        <div class="col-md-6 col-lg-4">
          <div class="p-3 rounded-3 h-100" style="background:#f8f9fa; border-left: 4px solid #198754;">
            <div class="fw-bold mb-1">③ Gate</div>
            <div class="text-muted" style="font-size:0.9rem">For each candidate, fork the library, apply the edit, and re-run a balanced out-of-sample probe set. Compute fixes and regressions against the current library baseline.</div>
          </div>
        </div>
        <div class="col-md-6 col-lg-4">
          <div class="p-3 rounded-3 h-100" style="background:#f8f9fa; border-left: 4px solid #fd7e14;">
            <div class="fw-bold mb-1">④ Accept or Discard</div>
            <div class="text-muted" style="font-size:0.9rem">A candidate is accepted only if it satisfies both a <em>net-improvement</em> and a <em>hard regression budget</em> condition — otherwise the library is left unchanged.</div>
          </div>
        </div>
        <div class="col-md-6 col-lg-4">
          <div class="p-3 rounded-3 h-100" style="background:#f8f9fa; border-left: 4px solid #dc3545;">
            <div class="fw-bold mb-1">⑤ Checkpoint</div>
            <div class="text-muted" style="font-size:0.9rem">Validate on a held-out val split after every epoch. Snapshot the library whenever val improves; restore the best checkpoint at the end.</div>
          </div>
        </div>
        <div class="col-md-6 col-lg-4 d-flex align-items-center justify-content-center">
          <div class="text-center p-3">
            <div class="text-muted mb-1" style="font-size:0.82rem">Acceptance criterion</div>
            <div class="p-2 rounded-3" style="background:#212529; color:#f8f9fa; font-size:0.88rem; font-family: monospace; line-height:1.8;">
              (fixes − fixes₀) − (regress − regress₀) &gt; 0<br>
              <span style="color:#86efac">and</span> regress ≤ regress₀
            </div>
          </div>
        </div>
      </div>

      <p class="text-muted" style="font-size:0.9rem">
        The gate is what keeps the library small and monotonically useful. At inference, the library averages <strong>5 skills and 5.6k tokens</strong>, while ungated memory baselines grow to 34–53k tokens. The matched-compute ablation shows the gain comes from the gate's <em>decision</em>, not the compute it consumes.
      </p>
    </div>
  </div>
</div>

<hr class="section-divider">

<!-- ============================================================ RESULTS -->
<div class="container">
  <div class="row justify-content-center">
    <div class="col-lg-11">
      <h2 class="text-center mb-5">Results</h2>

      <!-- Main results -->
      <h4 class="mb-3">Clinical Benchmarks</h4>
      <p class="text-muted mb-3" style="font-size:0.9rem">
        Test accuracy on MedAgentBench across five base models. GRASP is the strongest method on every model; gains range from +17.2 to +48.2 points over no-skills and +9.4 to +21.0 points over the strongest self-improvement baseline.
      </p>
      <div class="table-responsive mb-5">
        <table class="table table-bordered results-table">
          <thead>
            <tr>
              <th>Model</th>
              <th class="text-center">No Skills</th>
              <th class="text-center">Best Baseline</th>
              <th class="text-center">GRASP (ours)</th>
              <th class="text-center">Gain vs. No Skills</th>
              <th class="text-center">Gain vs. Best Baseline</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>gpt-oss-120b</td>
              <td class="text-center">40.6 <small class="text-muted">±3.9</small></td>
              <td class="text-center">67.8 <small class="text-muted">(Evo-MedAgent)</small></td>
              <td class="text-center best">88.8 <small class="text-muted">±5.8</small></td>
              <td class="text-center text-success fw-bold">+48.2</td>
              <td class="text-center text-success fw-bold">+21.0</td>
            </tr>
            <tr>
              <td>GPT-5.4 (low)</td>
              <td class="text-center">45.1 <small class="text-muted">±1.1</small></td>
              <td class="text-center">47.4 <small class="text-muted">(Batch Memory)</small></td>
              <td class="text-center best">85.4 <small class="text-muted">±10.4</small></td>
              <td class="text-center text-success fw-bold">+40.3</td>
              <td class="text-center text-success fw-bold">+38.0</td>
            </tr>
            <tr>
              <td>GPT-4.1</td>
              <td class="text-center">45.5 <small class="text-muted">±0.5</small></td>
              <td class="text-center">47.4 <small class="text-muted">(Batch Memory)</small></td>
              <td class="text-center best">84.9 <small class="text-muted">±0.9</small></td>
              <td class="text-center text-success fw-bold">+39.4</td>
              <td class="text-center text-success fw-bold">+37.5</td>
            </tr>
            <tr>
              <td>DeepSeek V4 Flash</td>
              <td class="text-center">47.7 <small class="text-muted">±2.1</small></td>
              <td class="text-center">55.9 <small class="text-muted">(SkillX)</small></td>
              <td class="text-center best">70.0 <small class="text-muted">±5.5</small></td>
              <td class="text-center text-success fw-bold">+22.3</td>
              <td class="text-center text-success fw-bold">+14.1</td>
            </tr>
            <tr>
              <td>Gemini 3.1 Flash Lite</td>
              <td class="text-center">54.2 <small class="text-muted">±1.5</small></td>
              <td class="text-center">55.2 <small class="text-muted">(Evo-MedAgent)</small></td>
              <td class="text-center best">71.4 <small class="text-muted">±1.8</small></td>
              <td class="text-center text-success fw-bold">+17.2</td>
              <td class="text-center text-success fw-bold">+16.2</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Non-medical -->
      <h4 class="mb-3">Non-Clinical Environments</h4>
      <p class="text-muted mb-3" style="font-size:0.9rem">
        GRASP on four AgentBench environments (gpt-oss-120b). The mechanism generalizes where tasks recur with verifiable structure; it is flat only where the action space is open-ended.
      </p>
      <div class="table-responsive mb-5">
        <table class="table table-bordered results-table" style="max-width:520px;">
          <thead>
            <tr>
              <th>Benchmark</th>
              <th class="text-center">No Skills</th>
              <th class="text-center">GRASP</th>
              <th class="text-center">Gain</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>ALFWorld</td>
              <td class="text-center">23.3 <small class="text-muted">±2.9</small></td>
              <td class="text-center best">51.7 <small class="text-muted">±7.6</small></td>
              <td class="text-center text-success fw-bold">+28.4</td>
            </tr>
            <tr>
              <td>WebShop</td>
              <td class="text-center">20.7 <small class="text-muted">±1.2</small></td>
              <td class="text-center best">41.3 <small class="text-muted">±8.1</small></td>
              <td class="text-center text-success fw-bold">+20.6</td>
            </tr>
            <tr>
              <td>DBBench</td>
              <td class="text-center">65.6 <small class="text-muted">±3.9</small></td>
              <td class="text-center best">70.6 <small class="text-muted">±1.0</small></td>
              <td class="text-center text-success fw-bold">+5.0</td>
            </tr>
            <tr>
              <td>OS Interaction</td>
              <td class="text-center">48.6 <small class="text-muted">±2.9</small></td>
              <td class="text-center">49.5 <small class="text-muted">±1.7</small></td>
              <td class="text-center text-muted">+0.9</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Cross-model transfer -->
      <h4 class="mb-3">Cross-Model Skill Transfer</h4>
      <p class="text-muted mb-3" style="font-size:0.9rem">
        Frozen GRASP skill libraries applied across models on MedAgentBench (gpt-oss-120b). Skills written by a stronger model improve weaker executors beyond what they learn for themselves; the reverse does not hold — an asymmetry no ungated baseline reproduces.
      </p>
      <div class="table-responsive mb-5">
        <table class="table table-bordered results-table">
          <thead>
            <tr>
              <th rowspan="2">Skill source</th>
              <th rowspan="2">Split</th>
              <th class="text-center" colspan="2">Executor: gpt-oss-120b</th>
              <th class="text-center" colspan="2">Executor: Gemini 3.1</th>
              <th class="text-center" colspan="2">Executor: GPT-5.4</th>
            </tr>
            <tr>
              <th class="text-center">Mean</th><th class="text-center">±SD</th>
              <th class="text-center">Mean</th><th class="text-center">±SD</th>
              <th class="text-center">Mean</th><th class="text-center">±SD</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td rowspan="2" class="text-muted fst-italic">None (baseline)</td>
              <td>Test</td>
              <td class="text-center">40.6</td><td class="text-center text-muted">3.9</td>
              <td class="text-center">54.2</td><td class="text-center text-muted">1.5</td>
              <td class="text-center">45.1</td><td class="text-center text-muted">1.1</td>
            </tr>
            <tr>
              <td>OOD</td>
              <td class="text-center">8.7</td><td class="text-center text-muted">3.2</td>
              <td class="text-center">18.1</td><td class="text-center text-muted">3.5</td>
              <td class="text-center">1.7</td><td class="text-center text-muted">1.6</td>
            </tr>
            <tr>
              <td rowspan="2">gpt-oss-120b</td>
              <td>Test</td>
              <td class="text-center best">88.8</td><td class="text-center text-muted">5.8</td>
              <td class="text-center best">79.7</td><td class="text-center text-muted">7.8</td>
              <td class="text-center">72.4</td><td class="text-center text-muted">15.8</td>
            </tr>
            <tr>
              <td>OOD</td>
              <td class="text-center">56.3</td><td class="text-center text-muted">14.5</td>
              <td class="text-center">36.1</td><td class="text-center text-muted">14.0</td>
              <td class="text-center">51.7</td><td class="text-center text-muted">2.9</td>
            </tr>
            <tr>
              <td rowspan="2">Gemini 3.1</td>
              <td>Test</td>
              <td class="text-center">65.6</td><td class="text-center text-muted">8.3</td>
              <td class="text-center">71.4</td><td class="text-center text-muted">1.8</td>
              <td class="text-center">69.3</td><td class="text-center text-muted">6.5</td>
            </tr>
            <tr>
              <td>OOD</td>
              <td class="text-center">57.8</td><td class="text-center text-muted">31.9</td>
              <td class="text-center">41.7</td><td class="text-center text-muted">20.9</td>
              <td class="text-center">58.9</td><td class="text-center text-muted">37.5</td>
            </tr>
            <tr>
              <td rowspan="2">GPT-5.4 (low)</td>
              <td>Test</td>
              <td class="text-center">76.0</td><td class="text-center text-muted">7.7</td>
              <td class="text-center">76.6</td><td class="text-center text-muted">10.9</td>
              <td class="text-center best">85.4</td><td class="text-center text-muted">10.4</td>
            </tr>
            <tr>
              <td>OOD</td>
              <td class="text-center best">77.8</td><td class="text-center text-muted">1.0</td>
              <td class="text-center best">71.1</td><td class="text-center text-muted">1.9</td>
              <td class="text-center best">80.6</td><td class="text-center text-muted">6.7</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Ablations -->
      <h4 class="mb-3">Ablations</h4>
      <p class="text-muted mb-3" style="font-size:0.9rem">
        MedAgentBench (gpt-oss-120b, 3 seeds). Removing the acceptance gate entirely — applying every edit unconditionally — falls to the no-skills baseline. The matched-compute variants confirm the gain is in the gate's <em>decision</em>, not the compute it spends.
      </p>
      <div class="table-responsive mb-2">
        <table class="table table-bordered results-table" style="max-width:520px;">
          <thead>
            <tr>
              <th>Method variant</th>
              <th class="text-center">Val*</th>
              <th class="text-center">Test</th>
            </tr>
          </thead>
          <tbody>
            <tr class="grasp-row">
              <td><strong>GRASP (full)</strong></td>
              <td class="text-center best">86.0 <small class="text-muted">±4.4</small></td>
              <td class="text-center best">88.8 <small class="text-muted">±5.8</small></td>
            </tr>
            <tr>
              <td class="ps-3 text-muted">w/o failure grouping</td>
              <td class="text-center">82.1 <small class="text-muted">±5.2</small></td>
              <td class="text-center">84.4 <small class="text-muted">±3.1</small></td>
            </tr>
            <tr>
              <td class="ps-3 text-muted">w/o regression budget</td>
              <td class="text-center">81.2 <small class="text-muted">±6.5</small></td>
              <td class="text-center">81.8 <small class="text-muted">±1.8</small></td>
            </tr>
            <tr>
              <td class="ps-3 text-muted">fixes-only selection</td>
              <td class="text-center">78.8 <small class="text-muted">±14.4</small></td>
              <td class="text-center">80.2 <small class="text-muted">±13.7</small></td>
            </tr>
            <tr>
              <td class="ps-3 text-muted">append-only</td>
              <td class="text-center">73.3 <small class="text-muted">±8.3</small></td>
              <td class="text-center">80.2 <small class="text-muted">±9.4</small></td>
            </tr>
            <tr>
              <td class="ps-3 text-muted">w/o acceptance gate (K=4)</td>
              <td class="text-center">65.4 <small class="text-muted">±9.7</small></td>
              <td class="text-center">63.5 <small class="text-muted">±3.9</small></td>
            </tr>
            <tr>
              <td class="ps-3 text-muted">w/o acceptance gate (K=1)</td>
              <td class="text-center">38.8 <small class="text-muted">±8.2</small></td>
              <td class="text-center">40.1 <small class="text-muted">±11.3</small></td>
            </tr>
            <tr>
              <td class="ps-3 text-muted">matched compute (proposer)</td>
              <td class="text-center">67.1 <small class="text-muted">±14.8</small></td>
              <td class="text-center">70.8 <small class="text-muted">±14.0</small></td>
            </tr>
            <tr>
              <td class="ps-3 text-muted">matched compute (random)</td>
              <td class="text-center">62.1 <small class="text-muted">±7.5</small></td>
              <td class="text-center">67.2 <small class="text-muted">±10.2</small></td>
            </tr>
          </tbody>
        </table>
      </div>

    </div>
  </div>
</div>

<hr class="section-divider">

<!-- ============================================================ SKILL BROWSER -->
<div class="container mb-5" id="skill-browser">
  <div class="row justify-content-center">
    <div class="col-lg-9">
      <h2 class="text-center mb-2">Learned Skill Library</h2>
      <p class="text-center text-muted mb-4" style="font-size:0.92rem;">
        13 representative skills learned by GRASP across clinical FHIR and non-clinical environments.
        Each was admitted by the regression gate: it fixes more failures than it causes regressions on the held-out probe.
      </p>

      <!-- Filters -->
      <div class="d-flex flex-wrap justify-content-center gap-2 mb-4" id="skill-filters"></div>

      <!-- Nav -->
      <div class="d-flex justify-content-center align-items-center gap-3 mb-3">
        <button class="btn btn-outline-secondary nav-btn" id="skill-prev">&#8592; Prev</button>
        <span id="skill-counter" class="text-muted">1 / 13</span>
        <button class="btn btn-outline-secondary nav-btn" id="skill-next">Next &#8594;</button>
      </div>

      <!-- Card -->
      <div id="skill-card-container"></div>
    </div>
  </div>
</div>

<hr class="section-divider">

<!-- ============================================================ BIBTEX -->
<section class="section" id="BibTeX">
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-lg-9">
        <h2 class="text-center mb-4">BibTeX</h2>
        <pre style="background:#f8f9fa; border-radius:8px; padding:1.2rem; font-size:0.85rem;"><code>@inproceedings{moll2026grasp,
  title  = {GRASP: Gated Regression-Aware Skill Proposer for Self-Improving LLM Agents},
  author = {Moll, Johannes and Corbeil, Jean-Philippe and Pan, Jiazhen and
            Hadamitzky, Martin and Rueckert, Daniel and Adams, Lisa and Bressem, Keno},
  booktitle = {Proceedings of the 2026 Conference on Empirical Methods in Natural Language Processing},
  year   = {2026}
}</code></pre>
      </div>
    </div>
  </div>
</section>

<!-- ============================================================ SKILL BROWSER JS -->
<script>
(function() {
  const DOMAIN_STYLES = {
    "MedAgentBench":    { cls: "clinical",    label: "MedAgentBench" },
    "MedAgentBench-v2": { cls: "clinical-v2", label: "MedAgentBench-v2" },
    "FHIR-AgentBench":  { cls: "clinical",    label: "FHIR-AgentBench" },
    "ALFWorld":         { cls: "alfworld",    label: "ALFWorld" },
    "WebShop":          { cls: "webshop",     label: "WebShop" },
    "DBBench":          { cls: "dbbench",     label: "DBBench" },
    "OS Interaction":   { cls: "os",          label: "OS Interaction" }
  };

  let skills = [];
  let filtered = [];
  let current = 0;
  let activeFilter = "all";

  function domainGroup(domain) {
    if (domain === "MedAgentBench" || domain === "MedAgentBench-v2" || domain === "FHIR-AgentBench") return "Clinical FHIR";
    return domain;
  }

  function renderFilters(skills) {
    const container = document.getElementById("skill-filters");
    const groups = {};
    skills.forEach(s => {
      const g = domainGroup(s.domain);
      groups[g] = (groups[g] || 0) + 1;
    });

    const filters = [["all", "All (" + skills.length + ")"],
      ...Object.entries(groups).map(([k, v]) => [k, k + " (" + v + ")"])];

    container.innerHTML = "";
    filters.forEach(([key, label]) => {
      const btn = document.createElement("button");
      btn.className = "filter-btn" + (key === "all" ? " active" : "");
      btn.textContent = label;
      btn.dataset.filter = key;
      btn.addEventListener("click", () => {
        activeFilter = key;
        current = 0;
        document.querySelectorAll(".filter-btn").forEach(b => b.classList.remove("active"));
        btn.classList.add("active");
        filtered = key === "all" ? skills : skills.filter(s => domainGroup(s.domain) === key);
        render();
      });
      container.appendChild(btn);
    });
  }

  function simpleMarkdown(text) {
    // minimal md -> html
    let out = text
      .replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;")
      // fenced code blocks
      .replace(/```[\w]*\n([\s\S]*?)```/g, "<pre><code>$1</code></pre>")
      // inline code
      .replace(/`([^`]+)`/g, "<code>$1</code>")
      // bold
      .replace(/\*\*([^*]+)\*\*/g, "<strong>$1</strong>")
      // headers
      .replace(/^### (.+)$/gm, "<h6>$1</h6>")
      .replace(/^## (.+)$/gm, "<h5>$1</h5>")
      .replace(/^# (.+)$/gm, "<h5>$1</h5>")
      // horizontal rule
      .replace(/^---+$/gm, "<hr>")
      // double newline -> paragraph break
      .replace(/\n\n/g, "\n<br>\n");
    return out;
  }

  function render() {
    const counter = document.getElementById("skill-counter");
    const container = document.getElementById("skill-card-container");

    if (filtered.length === 0) {
      counter.textContent = "0 / 0";
      container.innerHTML = "<p class='text-center text-muted'>No skills in this category.</p>";
      return;
    }

    const s = filtered[current];
    counter.textContent = (current + 1) + " / " + filtered.length;

    const ds = DOMAIN_STYLES[s.domain] || { cls: "clinical", label: s.domain };

    const tags = (s.tags || []).map(t =>
      "<span class='tag-pill me-1'>" + t + "</span>"
    ).join("");

    const actionCls = "action-badge-" + (s.action || "ADD");
    const provenanceNote = "v" + s.version + " &middot; epoch " + s.epoch + " &middot; <span class='badge " + actionCls + " px-2 py-1' style='font-size:0.72rem;'>" + (s.action || "ADD") + "</span>";

    const expandId = "skill-expand-" + current;
    const contentId = "skill-content-" + current;

    container.innerHTML = `
<div class="card skill-card">
  <div class="card-header d-flex justify-content-between align-items-center flex-wrap gap-2">
    <div class="d-flex align-items-center gap-2 flex-wrap">
      <span class="domain-badge ${ds.cls}">${ds.label}</span>
      <span class="model-pill">${s.model}</span>
    </div>
    <div class="text-muted small">${provenanceNote}</div>
  </div>
  <div class="card-body pt-3 pb-3">
    <h4 class="skill-title mb-2">${s.name.replace(/_/g, "&#8202;"+"_"+"&#8202;").replace(/_/g, "_")}</h4>
    <p class="skill-desc mb-3">${s.description}</p>
    <div class="d-flex flex-wrap gap-1 mb-4">${tags}</div>
    <div class="row text-center border-top border-bottom py-3 mb-4">
      <div class="col prov-stat fixes">
        <div class="val">+${s.fixes}</div>
        <div class="lbl">fixes</div>
      </div>
      <div class="col prov-stat regress">
        <div class="val">&#8722;${s.regressions}</div>
        <div class="lbl">regressions</div>
      </div>
      <div class="col prov-stat score">
        <div class="val">${s.probe_score}</div>
        <div class="lbl">probe score</div>
      </div>
    </div>
    <button class="btn btn-outline-dark btn-sm w-100 mb-0" id="${expandId}"
      onclick="(function(){
        var c=document.getElementById('${contentId}');
        var b=document.getElementById('${expandId}');
        if(c.style.display==='none'){c.style.display='block';b.textContent='Hide skill ↑';}
        else{c.style.display='none';b.textContent='Read full skill ↓';}
      })()">Read full skill &#8595;</button>
    <div id="${contentId}" style="display:none;" class="mt-3">
      <div class="skill-content-area">${simpleMarkdown(s.content)}</div>
    </div>
  </div>
</div>`;
  }

  document.getElementById("skill-prev").addEventListener("click", () => {
    if (filtered.length === 0) return;
    current = (current - 1 + filtered.length) % filtered.length;
    // collapse any open content
    render();
  });
  document.getElementById("skill-next").addEventListener("click", () => {
    if (filtered.length === 0) return;
    current = (current + 1) % filtered.length;
    render();
  });

  // Load skills from JSON
  fetch("{{ '/assets/json/grasp_skills.json' | relative_url }}")
    .then(r => r.json())
    .then(data => {
      skills = data;
      filtered = skills;
      renderFilters(skills);
      render();
    })
    .catch(err => {
      document.getElementById("skill-card-container").innerHTML =
        "<p class='text-center text-danger'>Could not load skills data.</p>";
    });
})();
</script>
