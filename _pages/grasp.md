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
      <h1 class="mb-4">GRASP: Gated Regression-Aware Skill Proposer for Self-Improving LLM Agents</h1>
      <div class="mb-3" style="font-size:1rem; line-height:2">
        <span style="white-space:nowrap">Johannes Moll<sup>1</sup></span>,
        <span style="white-space:nowrap">Jean-Philippe Corbeil<sup>2</sup></span>,
        <span style="white-space:nowrap">Jiazhen Pan<sup>1</sup></span>,
        <span style="white-space:nowrap">Martin Hadamitzky<sup>1</sup></span>,
        <span style="white-space:nowrap">Daniel Rueckert<sup>1</sup></span>,
        <span style="white-space:nowrap">Lisa Adams<sup>1,†</sup></span>,
        <span style="white-space:nowrap">Keno Bressem<sup>1,†</sup></span>
      </div>
      <div class="mb-3 text-muted" style="font-size:0.9rem">
        <sup>1</sup>Technical University of Munich &amp; TUM University Hospital
        <br><sup>2</sup>Microsoft Healthcare &amp; Life Sciences
        <br><sup>†</sup>Equal senior authorship
      </div>
      <!--div class="mb-4"-->
        <!--span class="badge rounded-pill px-3 py-2" style="background:#212529; color:white; font-size:0.9rem;">EMNLP 2026</span-->
      <!--/div-->
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
      <img src="{{ '/assets/img/emnlp26/grasp_banner3.png' | relative_url }}"
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
        We evaluate <strong>GRASP</strong> across five base models (gpt-oss-120b, DeepSeek V4 Flash, Gemini 3.1 Flash Lite, GPT-4.1, GPT-5.4) on two FHIR-based clinical benchmarks. On MedAgentBench, <strong>GRASP</strong> lifts gpt-oss-120b from 40.6% to 88.8%, exceeds the strongest of five self-improvement baselines by 21.0 points, and improves every other base model by 17.2 to 40.3 points. Ablations attribute the gain to comparative proposal generation, the acceptance gate, and the hard regression budget rather than to skill writing itself, which without validation is no better than using no skills. The mechanism generalizes beyond the clinical domain, improving agents on three of four non-clinical environments, and frozen libraries transfer across models. Skills from a stronger model improve weaker executors beyond what they learn for themselves while the reverse does not, an asymmetry that no ungated baseline reproduces.
      </p>
    </div>
  </div>
</div>

<hr class="section-divider">

<!-- ============================================================ METHOD -->
<div class="container">
  <div class="row justify-content-center">
    <div class="col-lg-10">
      <h2 class="text-center mb-2">How GRASP Works</h2>
      <p class="text-center text-muted mb-4" style="font-size:0.92rem;">
        GRASP maintains a small, versioned library of behavioral <em>skills</em> injected into the agent's context. After each training batch it proposes edits and admits them only if they pass a regression-aware probe. The example below traces a single skill being learned on MedAgentBench.
      </p>

      <!-- Step strip -->
      <div class="grasp-step-strip mb-4" id="grasp-strip"></div>

      <!-- Step content card -->
      <div class="card border-0 shadow-sm rounded-3 mb-3" id="grasp-step-card" style="min-height:340px;"></div>

      <!-- Nav -->
      <div class="d-flex justify-content-between align-items-center">
        <button class="btn btn-outline-secondary rounded-pill px-4" id="grasp-prev" style="font-size:0.9rem;">&#8592; Previous</button>
        <span id="grasp-step-label" class="text-muted" style="font-size:0.85rem;"></span>
        <button class="btn btn-outline-secondary rounded-pill px-4" id="grasp-next" style="font-size:0.9rem;">Next &#8594;</button>
      </div>
    </div>
  </div>
</div>

<style>
/* Step strip */
.grasp-step-strip {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0;
}
.grasp-step-node {
  display: flex;
  flex-direction: column;
  align-items: center;
  cursor: pointer;
  flex-shrink: 0;
}
.grasp-step-dot {
  width: 36px; height: 36px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-weight: 700; font-size: 0.9rem;
  border: 2.5px solid;
  transition: all 0.2s;
}
.grasp-step-dot.active {
  color: white;
  box-shadow: 0 2px 8px rgba(0,0,0,0.18);
  transform: scale(1.12);
}
.grasp-step-dot.inactive {
  background: white;
  opacity: 0.45;
}
.grasp-step-node-label {
  font-size: 0.72rem;
  margin-top: 5px;
  font-weight: 500;
  transition: all 0.2s;
  white-space: nowrap;
}
.grasp-step-node-label.active { font-weight: 700; }
.grasp-step-node-label.inactive { opacity: 0.45; }
.grasp-step-connector {
  height: 2.5px;
  flex: 1;
  min-width: 16px;
  max-width: 56px;
  margin-bottom: 20px;
  opacity: 0.25;
}

/* Step content */
.grasp-step-header {
  border-radius: 12px 12px 0 0;
  padding: 1rem 1.4rem 0.8rem;
}
.grasp-step-body {
  padding: 1.2rem 1.4rem;
}
.grasp-step-number {
  font-size: 0.78rem; font-weight: 600; letter-spacing: 0.04em;
  text-transform: uppercase; opacity: 0.75; margin-bottom: 2px;
}
.grasp-step-title {
  font-size: 1.25rem; font-weight: 700; margin: 0;
}
.grasp-step-desc {
  font-size: 0.92rem; color: #495057; margin-bottom: 1rem; line-height: 1.6;
}
.grasp-example-box {
  background: #1a1d23;
  border-radius: 8px;
  padding: 1rem 1.2rem;
  font-family: 'SFMono-Regular', 'Consolas', 'Liberation Mono', monospace;
  font-size: 0.78rem;
  line-height: 1.7;
  color: #cdd3de;
  overflow-x: auto;
  white-space: pre;
}
.grasp-example-label {
  font-size: 0.68rem; font-weight: 600; letter-spacing: 0.07em;
  text-transform: uppercase; color: #6c757d; margin-bottom: 0.5rem;
}
.ex-dim    { color: #6c757d; }
.ex-key    { color: #79c0ff; }
.ex-val    { color: #a5d6a7; }
.ex-err    { color: #f97583; }
.ex-ok     { color: #56d364; }
.ex-hi     { color: #ffd700; font-weight: 600; }
.ex-muted  { color: #8b949e; }
.ex-badge-add    { color: #56d364; font-weight: 700; }
.ex-badge-mod    { color: #ffd700; font-weight: 700; }
.ex-section { color: #79c0ff; font-weight: 600; }
</style>

<script>
(function() {
  const STEPS = [
    {
      color: "#0d6efd",
      label: "Rollout",
      title: "Rollout & Score",
      desc: "The skill-aware agent runs on every sample in the current training batch using the current skill library (initially empty). Each trajectory is scored, and failures receive a mechanism-specific label that pinpoints <em>why</em> it was wrong, not just that it was wrong.",
      example: `<span class="ex-dim">Epoch 0 · Batch 1 of 6 · 48 dev samples · 0 skills active</span>
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Task</span>  <span class="ex-muted">"What is the age of patient with MRN S2874099?"</span>

<span class="ex-key">→</span> GET /Patient?identifier=S2874099
<span class="ex-key">←</span> birthDate: <span class="ex-val">"1957-12-15"</span>  ·  ref: <span class="ex-val">2023-11-13</span>

  <span class="ex-muted">2023 − 1957 = 66  (month/day not checked)</span>

<span class="ex-key">→</span> FINISH(<span class="ex-err">[66]</span>)

<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-err">✗ FAIL</span>   expected <span class="ex-ok">[65]</span>  ·  got <span class="ex-err">[66]</span>
  mechanism label: <span class="ex-hi">age_off_by_one</span>
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-muted">Batch result: 31 / 48 correct (64.6%)</span>
<span class="ex-muted">Failures with label age_off_by_one: 11</span>`
    },
    {
      color: "#6610f2",
      label: "Propose",
      title: "Propose",
      desc: "Failures are grouped by mechanism label. For each group, a skill-writing model proposes <em>K</em> candidate edits — ADD, MODIFY, or REMOVE — seeing the failing traces, active skill summaries, and passing examples for contrast. Each candidate is one structured Markdown skill document.",
      example: `<span class="ex-dim">Failure group: age_off_by_one  (11 failures)</span>
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Skill writer input</span>
  <span class="ex-muted">· 11 failing traces  (birthday month/day ignored)</span>
  <span class="ex-muted">· 0 active skills in library</span>
  <span class="ex-muted">· 5 passing traces for contrast</span>
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Candidate 1 / 4</span>  <span class="ex-badge-add">ADD</span>  <span class="ex-hi">age_calculation_from_birthdate</span>

  <span class="ex-val">description:</span> <span class="ex-muted">Compute patient age from birthDate</span>
               <span class="ex-muted">using the task's reference time.</span>
  <span class="ex-val">tags:</span>  <span class="ex-muted">[age, patient, birthdate, fhir]</span>

  <span class="ex-muted">if ref month/day &lt; birth month/day → year_diff − 1</span>
  FINISH(<span class="ex-ok">[65]</span>)  not  FINISH(<span class="ex-err">[66]</span>)

<span class="ex-muted">3 further candidates generated …</span>`
    },
    {
      color: "#198754",
      label: "Gate",
      title: "Gate",
      desc: "Each candidate is evaluated on a balanced probe drawn from episodes completed earlier in the epoch, half previously failing and half previously passing. The probe is always out-of-sample relative to the batch that generated the proposal. Both the current library and the candidate library are run on the same probe to get a causal comparison.",
      example: `<span class="ex-section">Evaluating candidate</span>  <span class="ex-badge-add">ADD</span>  <span class="ex-hi">age_calculation_from_birthdate</span>
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Probe set</span>  <span class="ex-muted">(18 samples from earlier batches)</span>
  <span class="ex-muted">· 9 previously failing  ·  9 previously passing</span>

<span class="ex-section">Baseline run</span>  <span class="ex-muted">(current library, 0 skills)</span>
  fixes₀ <span class="ex-key">=</span> <span class="ex-val">0</span>   regressions₀ <span class="ex-key">=</span> <span class="ex-val">0</span>

<span class="ex-section">Candidate run</span>  <span class="ex-muted">(+ age_calculation_from_birthdate)</span>
  fixes  <span class="ex-key">=</span> <span class="ex-ok">11</span>   regressions  <span class="ex-key">=</span> <span class="ex-val">0</span>

<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Adjusted score</span>
  (11 − 0) − (0 − 0) <span class="ex-key">=</span> <span class="ex-hi">11</span>`
    },
    {
      color: "#fd7e14",
      label: "Accept",
      title: "Accept or Discard",
      desc: "The best-scoring candidate is accepted only if it satisfies both conditions of the acceptance criterion. If no candidate clears the bar, the library is left unchanged and never updates on faith. If the winner caused any regressions, a contrastive revision step asks the skill writer to narrow it before committing.",
      example: `<span class="ex-section">Best candidate</span>  <span class="ex-badge-add">ADD</span>  <span class="ex-hi">age_calculation_from_birthdate</span>  <span class="ex-muted">(score 11)</span>
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Acceptance check</span>

  <span class="ex-muted">(fixes − fixes₀) − (regressions − regressions₀) > 0</span>
  (11 − 0) − (0 − 0) <span class="ex-key">=</span> 11  <span class="ex-ok">> 0  ✓</span>

  <span class="ex-muted">regressions ≤ regressions₀</span>
  0 ≤ 0  <span class="ex-ok">✓</span>

<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-ok">→ ACCEPTED</span>  ·  library updated

<span class="ex-section">Skill library  (1 skill)</span>
  <span class="ex-ok">①</span>  <span class="ex-hi">age_calculation_from_birthdate</span>
     <span class="ex-muted">v1 · epoch 0 · +11 fixes · 0 regressions</span>`
    },
    {
      color: "#dc3545",
      label: "Checkpoint",
      title: "Checkpoint",
      desc: "After each epoch the agent is evaluated on the held-out validation split (no skill updates from val). If val accuracy improves, the library is snapshotted. After all epochs, the best-val checkpoint is restored as the final library, so a bad late epoch cannot degrade the result.",
      example: `<span class="ex-section">End of epoch 0</span>
<span class="ex-dim">─────────────────────────────────────────────────────────</span>
<span class="ex-muted">Val accuracy — no skills (baseline):  45.2%</span>
<span class="ex-hi">Val accuracy — 1 skill:               63.8%  ↑ +18.6 pp</span>

<span class="ex-ok">New best  →  snapshot saved</span>
<span class="ex-dim">─────────────────────────────────────────────────────────</span>
<span class="ex-section">Training continues …  (5 epochs total)</span>

<span class="ex-muted">epoch 1:  val 71.4%  ↑  snapshot saved</span>
<span class="ex-muted">epoch 2:  val 79.2%  ↑  snapshot saved  (4 skills)</span>
<span class="ex-muted">epoch 3:  val 83.1%  ↑  snapshot saved</span>
<span class="ex-muted">epoch 4:  val 82.7%  —  (no improvement, not saved)</span>
<span class="ex-dim">─────────────────────────────────────────────────────────</span>
<span class="ex-ok">Final library restored from epoch 3 checkpoint</span>
<span class="ex-hi">Test accuracy:  88.8%</span>  <span class="ex-muted">(was 40.6% without skills)</span>`
    }
  ];

  let current = 0;

  function renderStrip() {
    const strip = document.getElementById("grasp-strip");
    strip.innerHTML = "";
    STEPS.forEach((s, i) => {
      const node = document.createElement("div");
      node.className = "grasp-step-node";
      node.onclick = () => { current = i; render(); };

      const isActive = i === current;
      const dotCls = isActive ? "active" : "inactive";
      node.innerHTML = `
        <div class="grasp-step-dot ${dotCls}"
             style="border-color:${s.color};${isActive ? 'background:'+s.color+';' : 'color:'+s.color+';'}">
          ${i + 1}
        </div>
        <div class="grasp-step-node-label ${dotCls}" style="${isActive ? 'color:'+s.color+';' : ''}">${s.label}</div>`;
      strip.appendChild(node);

      if (i < STEPS.length - 1) {
        const conn = document.createElement("div");
        conn.className = "grasp-step-connector";
        conn.style.background = s.color;
        strip.appendChild(conn);
      }
    });
  }

  function renderCard() {
    const s = STEPS[current];
    const card = document.getElementById("grasp-step-card");
    card.style.borderTop = `4px solid ${s.color}`;
    card.innerHTML = `
      <div class="grasp-step-body">
        <div class="grasp-step-number" style="color:${s.color}">Step ${current + 1} of ${STEPS.length}</div>
        <h4 class="grasp-step-title mb-3">${s.title}</h4>
        <p class="grasp-step-desc">${s.desc}</p>
        <div class="grasp-example-label">Example run — MedAgentBench · gpt-oss-120b</div>
        <div class="grasp-example-box">${s.example}</div>
      </div>`;
  }

  function renderLabel() {
    document.getElementById("grasp-step-label").textContent =
      STEPS[current].label + "  (" + (current + 1) + " / " + STEPS.length + ")";
  }

  function render() {
    renderStrip();
    renderCard();
    renderLabel();
    document.getElementById("grasp-prev").disabled = current === 0;
    document.getElementById("grasp-next").disabled = current === STEPS.length - 1;
  }

  document.getElementById("grasp-prev").onclick = () => { if (current > 0) { current--; render(); } };
  document.getElementById("grasp-next").onclick = () => { if (current < STEPS.length - 1) { current++; render(); } };

  render();
})();
</script>

<hr class="section-divider">

<!-- ============================================================ EXTEND -->
<div class="container mb-2">
  <div class="row justify-content-center">
    <div class="col-lg-9">
      <h2 class="text-center mb-2">Extend GRASP</h2>
      <p class="text-center text-muted mb-4" style="font-size:0.92rem;">
        The codebase is designed to be extended. You can plug in your own self-improvement method and benchmark it against GRASP on the same tasks, or deploy GRASP on a new environment by implementing a single interface.
      </p>
      <div class="row g-3">
        <div class="col-md-6">
          <a href="{{ '/grasp/add-method/' | relative_url }}" class="text-decoration-none">
            <div class="card h-100 border-0 shadow-sm rounded-3 p-3" style="transition:box-shadow 0.15s;" onmouseover="this.style.boxShadow='0 4px 20px rgba(0,0,0,0.12)'" onmouseout="this.style.boxShadow=''">
              <div class="mb-2" style="font-size:1.4rem;">⚙️</div>
              <h5 class="fw-700 mb-1" style="font-size:1rem; font-weight:700;">Benchmark your method</h5>
              <p class="text-muted mb-0" style="font-size:0.88rem;">Subclass <code>grasp.Method</code> and run your own self-improvement approach on the same tasks GRASP uses for apples-to-apples comparison.</p>
            </div>
          </a>
        </div>
        <div class="col-md-6">
          <a href="{{ '/grasp/add-task/' | relative_url }}" class="text-decoration-none">
            <div class="card h-100 border-0 shadow-sm rounded-3 p-3" style="transition:box-shadow 0.15s;" onmouseover="this.style.boxShadow='0 4px 20px rgba(0,0,0,0.12)'" onmouseout="this.style.boxShadow=''">
              <div class="mb-2" style="font-size:1.4rem;">🔌</div>
              <h5 class="fw-700 mb-1" style="font-size:1rem; font-weight:700;">Add a new task</h5>
              <p class="text-muted mb-0" style="font-size:0.88rem;">Implement <code>grasp.Task</code> with three methods to deploy GRASP on any new environment, with optional hooks for sharper skill proposals.</p>
            </div>
          </a>
        </div>
      </div>
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
        Test accuracy on MedAgentBench across five base models. GRASP is the strongest method on every model, with gains of +17.2 to +48.2 points over no-skills and +9.4 to +21.0 points over the strongest self-improvement baseline.
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
        GRASP on four AgentBench environments (gpt-oss-120b). The mechanism generalizes where tasks recur with verifiable structure, and is flat only where the action space is open-ended.
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
        Frozen GRASP skill libraries applied across models on MedAgentBench (gpt-oss-120b). Skills written by a stronger model improve weaker executors beyond what they learn for themselves, but the reverse does not hold, an asymmetry no ungated baseline reproduces.
      </p>
      <div class="table-responsive mb-5">
        <table class="table table-bordered results-table">
          <thead>
            <tr>
              <th>Skill source</th>
              <th>Split</th>
              <th class="text-center">Executor: gpt-oss-120b</th>
              <th class="text-center">Executor: Gemini 3.1</th>
              <th class="text-center">Executor: GPT-5.4</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td rowspan="2" class="text-muted fst-italic">None (baseline)</td>
              <td>Test</td>
              <td class="text-center">40.6 <small class="text-muted">±3.9</small></td>
              <td class="text-center">54.2 <small class="text-muted">±1.5</small></td>
              <td class="text-center">45.1 <small class="text-muted">±1.1</small></td>
            </tr>
            <tr>
              <td>OOD</td>
              <td class="text-center">8.7 <small class="text-muted">±3.2</small></td>
              <td class="text-center">18.1 <small class="text-muted">±3.5</small></td>
              <td class="text-center">1.7 <small class="text-muted">±1.6</small></td>
            </tr>
            <tr>
              <td rowspan="2">gpt-oss-120b</td>
              <td>Test</td>
              <td class="text-center best">88.8 <small class="text-muted">±5.8</small></td>
              <td class="text-center best">79.7 <small class="text-muted">±7.8</small></td>
              <td class="text-center">72.4 <small class="text-muted">±15.8</small></td>
            </tr>
            <tr>
              <td>OOD</td>
              <td class="text-center">56.3 <small class="text-muted">±14.5</small></td>
              <td class="text-center">36.1 <small class="text-muted">±14.0</small></td>
              <td class="text-center">51.7 <small class="text-muted">±2.9</small></td>
            </tr>
            <tr>
              <td rowspan="2">Gemini 3.1</td>
              <td>Test</td>
              <td class="text-center">65.6 <small class="text-muted">±8.3</small></td>
              <td class="text-center">71.4 <small class="text-muted">±1.8</small></td>
              <td class="text-center">69.3 <small class="text-muted">±6.5</small></td>
            </tr>
            <tr>
              <td>OOD</td>
              <td class="text-center">57.8 <small class="text-muted">±31.9</small></td>
              <td class="text-center">41.7 <small class="text-muted">±20.9</small></td>
              <td class="text-center">58.9 <small class="text-muted">±37.5</small></td>
            </tr>
            <tr>
              <td rowspan="2">GPT-5.4 (low)</td>
              <td>Test</td>
              <td class="text-center">76.0 <small class="text-muted">±7.7</small></td>
              <td class="text-center">76.6 <small class="text-muted">±10.9</small></td>
              <td class="text-center best">85.4 <small class="text-muted">±10.4</small></td>
            </tr>
            <tr>
              <td>OOD</td>
              <td class="text-center best">77.8 <small class="text-muted">±1.0</small></td>
              <td class="text-center best">71.1 <small class="text-muted">±1.9</small></td>
              <td class="text-center best">80.6 <small class="text-muted">±6.7</small></td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Ablations -->
      <h4 class="mb-3">Ablations</h4>
      <p class="text-muted mb-3" style="font-size:0.9rem">
        MedAgentBench (gpt-oss-120b, 3 seeds). Removing the acceptance gate entirely (applying every edit unconditionally) falls to the no-skills baseline. The matched-compute variants confirm the gain is in the gate's <em>decision</em>, not the compute it spends.
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
        Each was admitted by the regression gate, fixing more failures than regressions on the held-out probe.
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
        <pre style="background:#f8f9fa; border-radius:8px; padding:1.2rem; font-size:0.85rem;"><code>@article{moll2026grasp,
  title  = {GRASP: Gated Regression-Aware Skill Proposer for Self-Improving LLM Agents},
  author = {Moll, Johannes and Corbeil, Jean-Philippe and Pan, Jiazhen and
            Hadamitzky, Martin and Rueckert, Daniel and Adams, Lisa and Bressem, Keno},
  journal={arXiv preprint },
  year={2026}
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
    <div class="d-flex flex-wrap gap-1 mb-3">${tags}</div>
    <div class="skill-content-area">${simpleMarkdown(s.content)}</div>
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
