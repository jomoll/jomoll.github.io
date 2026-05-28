---
layout: page
title: "Add Your Own Task or Benchmark"
permalink: /grasp/add-task/
nav: false
---

<style>
.back-link { font-size: 0.88rem; margin-bottom: 1.5rem; }
.back-link a { color: #6c757d; text-decoration: none; }
.back-link a:hover { color: #212529; }
.hook-card { background: #f8f9fa; border-radius: 8px; padding: 0.9rem 1.1rem; margin-bottom: 0.75rem; font-size: 0.9rem; }
.hook-card code { background: #e9ecef; padding: 0.1em 0.3em; border-radius: 3px; font-size: 0.85em; }
</style>

<p class="back-link">← <a href="{{ '/grasp/' | relative_url }}">Back to GRASP</a></p>

To run GRASP (or any `Method`) on a new environment, implement `grasp.Task`. It has three required methods and a few optional hooks that improve proposal quality.

---

## The contract

```python
from grasp import Task, Rollout

class MyTask(Task):
    name = "my-task"

    def samples(self, split):            # "dev" | "val" | "test"
        # return a list of dicts; the only required key is a stable "id".
        ...

    def rollout(self, sample, agent):    # run ONE episode
        # drive agent.inference(history, tools=None) against your environment,
        # then return a Rollout capturing the transcript and outcome.
        ...
        return Rollout(history=history, agent_actions=actions,
                       answer=final_answer, status="completed", raw=...)

    def evaluate(self, sample, rollout): # -> bool
        ...
```

### Rollout fields

The learning loop reads these fields — populate what applies:

- `history` — the chat transcript (`{"role", "content"}`; use role `"agent"` for the agent's turns)
- `agent_actions` — the agent's actions/tool calls as readable strings (used to describe failures to the skill writer)
- `answer` — the final answer text, if the task has one
- `status` — `"completed"`, or a short label such as `"agent invalid action"` / `"task limit reached"` / `"error"` that the gate treats specially
- `raw` — the native result, for your `evaluate`

### Optional hooks

<div class="hook-card">
  <strong><code>failure_tags(sample, rollout) -> list[str]</code></strong><br>
  Mechanism tags for failures. Grouping failures by tag before proposing skills sharpens proposals considerably — this is the single highest-value hook to implement.
</div>
<div class="hook-card">
  <strong><code>protocol_hook(first_user_content) -> str | None</code></strong><br>
  Inject an environment-specific tool reminder alongside the skill library in the agent's context.
</div>
<div class="hook-card">
  <strong><code>updater_task_family</code> / <code>updater_guidance</code> / <code>updater_failure_examples</code></strong><br>
  Domain labels and guidance threaded into the skill-writer prompt, helping it produce environment-appropriate skills.
</div>

The smallest complete example is `examples/quickstart/task.py` (rollout loop and graders) backed by an in-process mock environment. Copy it as a starting point.

---

## Config a task needs

A run config supplies the backend and loop hyperparameters; the task provides the data. Minimum:

```yaml
agent_preset: local              # resolved from <config dir>/agents/local.yaml
skills:
  base_dir: path/to/skills/base  # the read-only skeleton template lives here
cycle:
  epochs: 3
  update_every: 100
  grpo_k: 3
  grpo_eval_n: 8
```

---

## Wiring an AgentBench environment

`benchmarks/AgentBench` ships ten task families; four are wired for the paper (`os`, `dbbench`, `webshop`, `alfworld`). The other six — **avalon, card_game, kg, ltp, mind2web, task_assembly** — have task servers and configs but no GRASP wiring yet. Two ways to reach them:

**Option 1: In-process Task (recommended)**

Write a `Task` whose `rollout` drives the environment directly and whose `evaluate` calls that environment's grader, exactly what the quickstart does for FHIR. You provide `samples` from the task's data split.

**Option 2: Wrap a running AgentBench worker**

AgentBench runs tasks behind a client/server worker (`TaskClient.run_sample(index, agent)`). A thin `Task` can start or connect to that worker and translate its `TaskClientOutput` into a `Rollout` (map `history`, the final answer, and status). This reuses the benchmark's existing environment and grader unchanged.

Either way, splits come from `Task.samples()`, so you control train/val/test without touching the core. Define `failure_tags` for the environment's characteristic failures and set `updater_task_family` to get sharper proposals.
