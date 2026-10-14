---
layout: page
permalink: /onco-agent/
title: Skill-Guided Agentic Reasoning for Longitudinal Myeloma Records
description: Skill-guided agentic reasoning enables longitudinal synthesis of myeloma records at expert-level concordance (npj Precision Oncology, 2026)
nav: false
og_image: 
---

<script>
(function() {
  var prev = document.documentElement.getAttribute('data-theme');
  document.documentElement.setAttribute('data-theme', 'light');
  window.addEventListener('pagehide', function() {
    if (prev === null) document.documentElement.removeAttribute('data-theme');
    else document.documentElement.setAttribute('data-theme', prev);
  });
})();
</script>

<style>
.page-header,
.post-header,
h1.post-title,
header.post-header {
    display: none !important;
}
.section-divider { border: none; border-top: 2px solid #e9ecef; margin: 3rem 0; }

/* Widen this page beyond the site-wide max_width */
.container[role="main"] { max-width: 1140px; }
.container[role="main"] .container { max-width: none; padding-left: 0; padding-right: 0; }

/* Key findings */
.oa-finding {
  display: flex;
  align-items: center;
  gap: 1.4rem;
  border-left: 4px solid;
  border-radius: 10px;
  padding: 1rem 1.4rem;
  background: #f8f9fa;
}
.oa-finding-value {
  flex: 0 0 9.5rem;
  white-space: nowrap;
  font-size: 1.9rem; font-weight: 700; line-height: 1.1;
}
@media (max-width: 575px) {
  .oa-finding { flex-direction: column; align-items: flex-start; gap: 0.35rem; }
  .oa-finding-value { flex-basis: auto; }
}
.oa-finding-label {
  font-size: 0.9rem; font-weight: 600; color: #212529; margin-bottom: 0.3rem;
}
.oa-finding-detail {
  font-size: 0.82rem; color: #6c757d; line-height: 1.5; margin: 0;
}
</style>

<!-- ============================================================ HERO -->
<div class="container mt-5">
  <div class="row justify-content-center text-center">
    <div class="col-12">
      <h1 class="mb-4">Skill-Guided Agentic Reasoning Enables Longitudinal Synthesis of Myeloma Records at Expert-Level Concordance</h1>
      <div class="mb-3" style="font-size:1rem; line-height:2">
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
      <div class="mb-3 text-muted" style="font-size:0.9rem">
        <sup>†</sup>Equal contribution &nbsp;|&nbsp; <sup>‡</sup>Equal senior contribution
      </div>
      <div class="mb-4">
        <span class="badge rounded-pill px-3 py-2" style="background:#00507a; color:white; font-size:0.9rem;">Published in npj Precision Oncology &middot; 2026</span>
      </div>
      <div class="mt-2 mb-4">
        <a href="https://www.nature.com/articles/s41698-026-01733-2" target="_blank" class="btn btn-dark btn-lg rounded-pill me-2 mb-2">
          <i class="fas fa-file-pdf me-1"></i> Paper
        </a>
        <a href="https://github.com/jomoll/onco-agent" target="_blank" class="btn btn-dark btn-lg rounded-pill me-2 mb-2">
          <i class="fab fa-github me-1"></i> Code
        </a>
      </div>
    </div>
  </div>
</div>

<!-- ============================================================ KEY FINDINGS -->
<div class="container mb-5">
  <div class="row justify-content-center">
    <div class="col-12">
      <h2 class="text-center mb-2">Key Findings</h2>
      <p class="text-center text-muted mb-4" style="font-size:0.92rem;">
        811 patients &middot; 44,962 documents &middot; 1,334,677 laboratory values &middot; 469 expert-adjudicated patient-question pairs
      </p>
      <div class="row g-3">
        <div class="col-12">
          <div class="oa-finding" style="border-left-color:#0d6efd;">
            <div class="oa-finding-value" style="color:#0d6efd;">80.1%</div>
            <div class="oa-finding-text">
              <div class="oa-finding-label">Above the non-agentic ceiling</div>
              <p class="oa-finding-detail">Iterative RAG (75.7%) and full-context input (75.8%) converge on a shared ceiling. The skill-guided agent exceeds both.</p>
            </div>
          </div>
        </div>
        <div class="col-12">
          <div class="oa-finding" style="border-left-color:#6f42c1;">
            <div class="oa-finding-value" style="color:#6f42c1;">79.0%</div>
            <div class="oa-finding-text">
              <div class="oa-finding-label">Skills drive the aggregate gain</div>
              <p class="oa-finding-detail">Giving iterative RAG the same clinical skill library matches the agent overall. Removing the skills from the agent drops it to 76.6%.</p>
            </div>
          </div>
        </div>
        <div class="col-12">
          <div class="oa-finding" style="border-left-color:#198754;">
            <div class="oa-finding-value" style="color:#198754;">+10.3 pp</div>
            <div class="oa-finding-text">
              <div class="oa-finding-label">Agentic execution pays off on long records</div>
              <p class="oa-finding-detail">Over skill-augmented RAG in the top decile of record length (<em>p</em> = 0.017; exploratory, 10 patients). On criteria-based synthesis, +11.2 pp over full context.</p>
            </div>
          </div>
        </div>
        <div class="col-12">
          <div class="oa-finding" style="border-left-color:#dc3545;">
            <div class="oa-finding-value" style="color:#dc3545;">57.8%</div>
            <div class="oa-finding-text">
              <div class="oa-finding-label">Fewer errors, heavier errors</div>
              <p class="oa-finding-detail">Error rate (12.2%) is comparable to expert disagreement (13.6%), but 57.8% of system errors are clinically significant versus 18.8% of expert disagreements.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ============================================================ ABSTRACT -->
<div class="container mt-4">
  <div class="row justify-content-center">
    <div class="col-12">
      <h2 class="text-center mb-4">Abstract</h2>
      <p class="text-justify">
        Patients with multiple myeloma accumulate hundreds of clinical documents over years of sequential therapy, and every treatment decision depends on synthesis across that history. Whether large language model–based systems can match expert agreement on this task, and where they fail, has not been established. On longitudinal records of 811 patients treated over 25 years (44,962 documents and 1,334,677 laboratory values), an agentic reasoning system guided by an indexed clinical skill library was compared against single-pass retrieval-augmented generation (RAG), iterative RAG, iterative RAG augmented with the same skill library, and full-context input on 469 expert-adjudicated patient-question pairs, with an exploratory cross-dataset evaluation on MIMIC-IV. The skill-guided agent exceeded the ceiling at which iterative RAG (75.7%) and full-context input (75.8%) converged, reaching 80.1% concordance, with its advantage widening on the most complex tasks (+11.2 percentage points) and longest records. Providing the same skill library to iterative RAG matched the agent in aggregate (79.0%) and on shorter records, whereas the agent retained a significant advantage on the longest records (+10.3 percentage points in the top decile, <em>p</em> = 0.017) and a numerical, non-significant advantage on the most complex questions (+5.4 percentage points). The aggregate error rate (12.2%) was comparable to expert disagreement (13.6%), but a higher proportion of system errors were clinically significant (57.8 versus 18.8%).
      </p>
    </div>
  </div>
</div>

<hr class="section-divider">

<!-- ============================================================ METHOD -->
<div class="container">
  <div class="row justify-content-center">
    <div class="col-12">
      <h2 class="text-center mb-2">How Onco-Agent Works</h2>
      <p class="text-center text-muted mb-4" style="font-size:0.92rem;">
        Onco-Agent separates clinical reasoning from language generation. Question-specific reasoning protocols come from an indexed clinical <em>skill library</em>, evidence is gathered by an explicit tool-use plan, and contradictions are resolved by deterministic policies before the answer is written. The example below follows one eligibility question through the pipeline.
      </p>

      <!-- Step strip -->
      <div class="oa-step-strip mb-4" id="oa-strip"></div>

      <!-- Step content card -->
      <div class="card border-0 shadow-sm rounded-3 mb-3" id="oa-step-card" style="min-height:340px;"></div>

      <!-- Nav -->
      <div class="d-flex justify-content-between align-items-center">
        <button class="btn btn-outline-secondary rounded-pill px-4" id="oa-prev" style="font-size:0.9rem;">&#8592; Previous</button>
        <span id="oa-step-label" class="text-muted" style="font-size:0.85rem;"></span>
        <button class="btn btn-outline-secondary rounded-pill px-4" id="oa-next" style="font-size:0.9rem;">Next &#8594;</button>
      </div>
    </div>
  </div>
</div>

<style>
/* Step strip */
.oa-step-strip {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0;
}
.oa-step-node {
  display: flex;
  flex-direction: column;
  align-items: center;
  cursor: pointer;
  flex-shrink: 0;
}
.oa-step-dot {
  width: 36px; height: 36px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-weight: 700; font-size: 0.9rem;
  border: 2.5px solid;
  transition: all 0.2s;
}
.oa-step-dot.active {
  color: white;
  box-shadow: 0 2px 8px rgba(0,0,0,0.18);
  transform: scale(1.12);
}
.oa-step-dot.inactive {
  background: white;
  opacity: 0.45;
}
.oa-step-node-label {
  font-size: 0.72rem;
  margin-top: 5px;
  font-weight: 500;
  transition: all 0.2s;
  white-space: nowrap;
}
.oa-step-node-label.active { font-weight: 700; }
.oa-step-node-label.inactive { opacity: 0.45; }
.oa-step-connector {
  height: 2.5px;
  flex: 1;
  min-width: 16px;
  max-width: 56px;
  margin-bottom: 20px;
  opacity: 0.25;
}

/* Step content */
.oa-step-body {
  padding: 1.2rem 1.4rem;
}
.oa-step-number {
  font-size: 0.78rem; font-weight: 600; letter-spacing: 0.04em;
  text-transform: uppercase; opacity: 0.75; margin-bottom: 2px;
}
.oa-step-title {
  font-size: 1.25rem; font-weight: 700; margin: 0;
}
.oa-step-desc {
  font-size: 0.92rem; color: #495057; margin-bottom: 1rem; line-height: 1.6;
}
.oa-example-box {
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
.oa-example-label {
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
.ex-section { color: #79c0ff; font-weight: 600; }
</style>

<script>
(function() {
  const STEPS = [
    {
      color: "#0d6efd",
      label: "Assess",
      title: "Assess Question & Select Skills",
      desc: "The question is analysed for clinical intent, required and still-missing information, and complexity. In parallel, the model selects matching modules from the indexed clinical skill library: <em>workflow</em> skills (how to decompose the task), <em>parsing</em> skills (abbreviations, German date formats, drug synonyms), <em>style</em> skills (answer templates) and <em>policy</em> skills (precedence rules for conflicting evidence). Keyword fallbacks and deterministic policy attachment keep the right protocols active even when the model omits them. On average 6.7 of 42 modules are loaded (~8k instead of ~49k tokens).",
      example: `<span class="ex-dim">Patient P-0417 · 63 documents · 2,418 laboratory values</span>
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Question</span>  <span class="ex-muted">"Is this patient eligible for BCMA-directed CAR-T therapy?"</span>

<span class="ex-section">Assessment</span>
  intent      <span class="ex-val">multi-criterion eligibility decision</span>
  complexity  <span class="ex-hi">Level 3</span> <span class="ex-muted">· criteria-based synthesis</span>
  required    <span class="ex-muted">prior lines · drug-class exposure (IMiD, PI, anti-CD38)</span>
              <span class="ex-muted">status on last line · organ function · performance status</span>
  missing     <span class="ex-err">all of the above</span>
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Selected skills</span>  <span class="ex-muted">(7)</span>
  <span class="ex-key">workflow</span>  <span class="ex-hi">workflows.eligibility_assessment</span>
  <span class="ex-key">workflow</span>  workflows.refractory_classification
  <span class="ex-key">parsing </span>  parsing.therapy_normalization
  <span class="ex-key">parsing </span>  parsing.de_date_formats
  <span class="ex-key">style   </span>  style.question_types.eligibility   <span class="ex-muted">(keyword fallback)</span>
  <span class="ex-key">style   </span>  style.structured_annotation        <span class="ex-muted">(always on)</span>
  <span class="ex-key">policy  </span>  policy.plan_vs_administered        <span class="ex-muted">(auto-attached)</span>`
    },
    {
      color: "#6f42c1",
      label: "Plan",
      title: "Draft a Tool-Use Plan",
      desc: "Before any evidence is retrieved, the agent drafts an ordered tool-use plan as structured JSON. Each step names an objective, the tool and its arguments, the evidence it must produce, and a stopping rule, and the plan carries global stopping conditions. The selected workflow skill shapes the plan: here, the eligibility checklist becomes one retrieval step per criterion. Invalid or empty plans are repaired and regenerated.",
      example: `<span class="ex-section">Tool-use plan</span>  <span class="ex-muted">(from workflows.eligibility_assessment)</span>
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-hi">1</span>  Reconstruct therapy history
   <span class="ex-key">retrieve_reports</span>(query=<span class="ex-val">"therapy line daratumumab lenalidomide bortezomib"</span>,
                    report_type=<span class="ex-val">["doctor_letter", "tumor_board"]</span>, time_scope=<span class="ex-val">"all"</span>)
   <span class="ex-muted">needs: lines of therapy, exposure per drug class</span>

<span class="ex-hi">2</span>  Response to most recent line
   <span class="ex-key">retrieve_reports</span>(query=<span class="ex-val">"progression remission response"</span>, time_scope=<span class="ex-val">"latest"</span>)
   <span class="ex-muted">needs: refractory / progression status</span>

<span class="ex-hi">3</span>  Organ function
   <span class="ex-key">retrieve_lab_values</span>(lab_keys=<span class="ex-val">["creatinine", "bilirubin", "platelets"]</span>,
                       time_scope=<span class="ex-val">"latest"</span>)

<span class="ex-hi">4</span>  Performance status &amp; active infections
   <span class="ex-key">retrieve_reports</span>(query=<span class="ex-val">"ECOG performance status infection"</span>, time_scope=<span class="ex-val">"latest"</span>)
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Stop when</span>  <span class="ex-muted">every criterion has supporting evidence or is confirmed undocumented</span>`
    },
    {
      color: "#198754",
      label: "Retrieve",
      title: "Execute Tools Iteratively",
      desc: "The plan is executed step by step for up to eight rounds. A structured memory state (query, accumulated evidence, still-missing information, stopping conditions) is updated after every round and decides whether to call a tool, advance, or stop. Report retrieval supports document-type and date filters, laboratory values are fetched by canonical marker, and staging scores (ISS, R-ISS, R2-ISS, HCT-CI) are computed by deterministic calculators rather than by the language model. Duplicate queries are blocked, and empty results progressively broaden the search.",
      example: `<span class="ex-section">Round 1</span>  <span class="ex-key">retrieve_reports</span> <span class="ex-muted">→ 6 sections</span>
  <span class="ex-val">[1]</span> 2025-10-09 doctor_letter  <span class="ex-muted">"… after 3 prior lines incl. lenalidomide, bortezomib …"</span>
  <span class="ex-val">[2]</span> 2023-05-29 tumor_board    <span class="ex-muted">"Recommendation: daratumumab-Rd"</span>
  <span class="ex-val">[3]</span> 2023-07-14 doctor_letter  <span class="ex-muted">"Dara-Rd cycle 1 administered …"</span>
  <span class="ex-muted">…</span>
<span class="ex-section">Round 2</span>  <span class="ex-key">retrieve_reports</span>  time_scope=latest <span class="ex-muted">→ 0 results</span>
  <span class="ex-err">empty</span>  <span class="ex-muted">→ retry with top_k doubled</span>  <span class="ex-muted">→ 2 sections</span>
  <span class="ex-val">[4]</span> 2025-10-09 doctor_letter  <span class="ex-muted">"Progression on pomalidomide-dexamethasone"</span>
<span class="ex-section">Round 3</span>  <span class="ex-key">retrieve_lab_values</span> <span class="ex-muted">→ 3 markers</span>
  <span class="ex-val">[5]</span> 2026-02-14 creatinine 0.9 mg/dL · bilirubin 0.6 mg/dL · platelets 142 G/L
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Memory state</span>  <span class="ex-muted">(after round 3)</span>
  evidence  <span class="ex-ok">IMiD ✓  PI ✓  anti-CD38 ✓  progression ✓  organ function ✓</span>
  missing   <span class="ex-err">performance status</span>  <span class="ex-muted">→ continue with step 4</span>`
    },
    {
      color: "#fd7e14",
      label: "Resolve",
      title: "Resolve Conflicting Evidence",
      desc: "Longitudinal records contradict themselves: plans change, letters copy outdated history forward, and documents disagree. A deterministic policy engine ranks the retrieved evidence by temporal authority and recency and applies the attached policy skills, for example that an administered therapy overrides a documented plan. It returns a structured resolution (<em>select</em>, <em>abstain</em> or <em>conflict</em>) that the answer must respect.",
      example: `<span class="ex-section">Policy engine</span>
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-hi">policy.plan_vs_administered</span>
  <span class="ex-val">[2]</span> 2023-05-29 tumor_board    <span class="ex-muted">planned       Dara-Rd</span>
  <span class="ex-val">[3]</span> 2023-07-14 doctor_letter  <span class="ex-muted">administered  Dara-Rd, cycle 1</span>
  <span class="ex-key">→</span> anti-CD38 exposure counted from <span class="ex-val">[3]</span>  <span class="ex-muted">(administration confirmed)</span>

<span class="ex-hi">policy.temporal_authority</span>
  <span class="ex-muted">status on current line:</span> most recent document wins
  <span class="ex-key">→</span> <span class="ex-val">[4]</span> 2025-10-09  progression on Pom-Dex
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Resolution</span>  <span class="ex-ok">select</span>  <span class="ex-muted">· no unresolved conflicts</span>`
    },
    {
      color: "#dc3545",
      label: "Answer",
      title: "Synthesize a Cited Answer",
      desc: "Retrieved context is deduplicated and numbered, then the answer is written using the style skills and the policy resolution. Every answer follows a two-line format: a schema-aligned <em>Answer</em> and a short <em>Reasoning</em> with inline citations to source documents. Citations are validated against the retrieved context, and references to sources that were never retrieved are flagged as potential hallucinations.",
      example: `<span class="ex-section">Answer:</span>     <span class="ex-ok">Yes</span>
<span class="ex-section">Reasoning:</span>  The patient has received an IMiD <span class="ex-val">[1]</span>, a proteasome
            inhibitor <span class="ex-val">[1]</span> and an anti-CD38 antibody <span class="ex-val">[3]</span>, progressed on
            the most recent line <span class="ex-val">[4]</span>, and has adequate organ function <span class="ex-val">[5]</span>.
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-section">Sources</span>
  <span class="ex-val">[1]</span> 2025-10-09  doctor_letter
  <span class="ex-val">[3]</span> 2023-07-14  doctor_letter
  <span class="ex-val">[4]</span> 2025-10-09  doctor_letter
  <span class="ex-val">[5]</span> 2026-02-14  laboratory · creatinine, bilirubin, platelets
<span class="ex-dim">────────────────────────────────────────────────────</span>
<span class="ex-muted">Citation check: 4 / 4 citations resolve to retrieved context</span>  <span class="ex-ok">✓</span>`
    }
  ];

  let current = 0;

  function renderStrip() {
    const strip = document.getElementById("oa-strip");
    strip.innerHTML = "";
    STEPS.forEach((s, i) => {
      const node = document.createElement("div");
      node.className = "oa-step-node";
      node.onclick = () => { current = i; render(); };

      const isActive = i === current;
      const dotCls = isActive ? "active" : "inactive";
      node.innerHTML = `
        <div class="oa-step-dot ${dotCls}"
             style="border-color:${s.color};${isActive ? 'background:'+s.color+';' : 'color:'+s.color+';'}">
          ${i + 1}
        </div>
        <div class="oa-step-node-label ${dotCls}" style="${isActive ? 'color:'+s.color+';' : ''}">${s.label}</div>`;
      strip.appendChild(node);

      if (i < STEPS.length - 1) {
        const conn = document.createElement("div");
        conn.className = "oa-step-connector";
        conn.style.background = s.color;
        strip.appendChild(conn);
      }
    });
  }

  function renderCard() {
    const s = STEPS[current];
    const card = document.getElementById("oa-step-card");
    card.style.borderTop = `4px solid ${s.color}`;
    card.innerHTML = `
      <div class="oa-step-body">
        <div class="oa-step-number" style="color:${s.color}">Step ${current + 1} of ${STEPS.length}</div>
        <h4 class="oa-step-title mb-3">${s.title}</h4>
        <p class="oa-step-desc">${s.desc}</p>
        <div class="oa-example-label">Illustrative example — synthetic patient · gpt-oss-120b</div>
        <div class="oa-example-box">${s.example}</div>
      </div>`;
  }

  function renderLabel() {
    document.getElementById("oa-step-label").textContent =
      STEPS[current].label + "  (" + (current + 1) + " / " + STEPS.length + ")";
  }

  function render() {
    renderStrip();
    renderCard();
    renderLabel();
    document.getElementById("oa-prev").disabled = current === 0;
    document.getElementById("oa-next").disabled = current === STEPS.length - 1;
  }

  document.getElementById("oa-prev").onclick = () => { if (current > 0) { current--; render(); } };
  document.getElementById("oa-next").onclick = () => { if (current < STEPS.length - 1) { current++; render(); } };

  render();
})();
</script>

<hr class="section-divider">

<!-- ============================================================ DEMO -->
<div class="container">
  <div class="row justify-content-center">
    <div class="col-12">
      <h2 class="text-center mb-4">Demo</h2>
      <div class="row g-3 text-center">
        <div class="col-md-4">
          <video controls muted playsinline style="width:100%; border-radius:8px;">
            <source src="{{ '/assets/video/example_1.mov' | relative_url }}" type="video/mp4">
          </video>
          <div class="mt-1">Single-document lookup</div>
        </div>
        <div class="col-md-4">
          <video controls muted playsinline style="width:100%; border-radius:8px;">
            <source src="{{ '/assets/video/example_2.mov' | relative_url }}" type="video/mp4">
          </video>
          <div class="mt-1">Temporal reasoning</div>
        </div>
        <div class="col-md-4">
          <video controls muted playsinline style="width:100%; border-radius:8px;">
            <source src="{{ '/assets/video/example_3.mov' | relative_url }}" type="video/mp4">
          </video>
          <div class="mt-1">Multi-criteria synthesis</div>
        </div>
      </div>
    </div>
  </div>
</div>

<hr class="section-divider">

<!-- ============================================================ BIBTEX -->
<div class="container mb-5">
  <div class="row justify-content-center">
    <div class="col-12">
      <h2 class="text-center mb-4">BibTeX</h2>
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
