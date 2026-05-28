---
layout: page
title: "Benchmark Your Own Self-Improvement Method"
permalink: /grasp/add-method/
nav: false
---

<style>
.back-link { font-size: 0.88rem; margin-bottom: 1.5rem; }
.back-link a { color: #6c757d; text-decoration: none; }
.back-link a:hover { color: #212529; }
.baseline-table th { background: #212529; color: white; font-size: 0.85rem; font-weight: 600; }
.baseline-table td { font-size: 0.85rem; vertical-align: middle; }
</style>

<p class="back-link">← <a href="{{ '/grasp/' | relative_url }}">Back to GRASP</a></p>

GRASP is one point in a space of methods that improve an agent from its own experience. The harness lets you drop in your own method and run it on the same tasks GRASP uses, so comparisons are apples-to-apples.

---

## The contract

A method is a subclass of `grasp.Method`. The harness constructs it with a resolved config, a run directory to write into, and the `Task` to learn on, then calls `run()` once.

```python
from grasp import Method

class MyMethod(Method):
    # self.config: dict   self.run_dir: Path   self.task: Task
    def run(self) -> None:
        dev = self.task.samples("dev")
        val = self.task.samples("val")

        for epoch in range(self.config["cycle"]["epochs"]):
            for sample in dev:
                rollout = self.task.rollout(sample, self._agent())
                correct = self.task.evaluate(sample, rollout)
                # ... update your memory / skills / prompt from failures ...

            # monitor on val (do not learn from it)
            score = sum(self.task.evaluate(s, self.task.rollout(s, self._agent()))
                        for s in val) / len(val)
            # ... write artifacts into self.run_dir ...
```

You build the executing agent with `grasp.agent.build_agent(self.config["agent"])`. If your method injects learned context, wrap the agent the way GRASP does in `grasp/cycle.py`.

### Conventional outputs

Not enforced, but writing these makes your runs comparable to GRASP's with the same tooling:

- `val_scores.json` — a list of `{epoch, score, ...}` (the learning curve)
- per-epoch logs of what the method did
- the learned artifact (skill/memory library) under `run_dir/`

---

## Running it

```python
from grasp import run_method

run_method(MyMethod, MyTask(), "path/to/config.yaml", agent="local")
```

`run_method` loads the config, resolves the backend (CLI `agent` > `GRASP_BACKEND` env > config `agent_preset`), creates the run directory, and calls `MyMethod(config, run_dir, task).run()`.

---

## Worked references: the five baselines

The paper implements five self-improvement baselines alongside GRASP, one per benchmark directory. They predate the `Method` base class but follow the same `__init__(config, run_dir, …)` + `run()` shape and are the best concrete templates to read and diff against.

<div class="table-responsive mt-3">
<table class="table table-bordered baseline-table">
  <thead>
    <tr><th>Entry point</th><th>Paper name</th><th>Idea</th></tr>
  </thead>
  <tbody>
    <tr><td><code>grasp</code></td><td><strong>GRASP</strong> (ours)</td><td>Regression-gated skill library</td></tr>
    <tr><td><code>memory_cycle</code></td><td>Sequential memory</td><td>Append lessons after each sample</td></tr>
    <tr><td><code>batch_memory_cycle</code></td><td>Batch memory</td><td>Summarize a batch into memory</td></tr>
    <tr><td><code>expel_cycle</code></td><td>ExpeL</td><td>Insight extraction from successes and failures</td></tr>
    <tr><td><code>evo_memory_cycle</code></td><td>Evo-MedAgent</td><td>Evolutionary memory updates</td></tr>
    <tr><td><code>skillx_cycle</code></td><td>SkillX</td><td>Skill extraction baseline</td></tr>
  </tbody>
</table>
</div>

Each `*_cycle.py` entry point lives in `benchmarks/MedAgentBench/src/` alongside its supporting package. To benchmark a new method, implement `Method.run()` and run it on the same `Task` and config.
