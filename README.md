# Leo Aarons-Ditson

UCL-trained physicist building and evaluating agentic AI systems, with a focus on tool use, reliability and measurable model behaviour.

BSc Physics and Postgraduate Certificate in Physics (Distinction), UCL · London

I turn quantitative and operational problems into working systems: bounded agent workflows, deterministic checks where a rule beats a model, and saved traces. I care where models fail as much as where they succeed. I set the questions, designs and acceptance checks; Claude Code or Codex writes most of the code.

## Start here

If you have five minutes, these four projects show the clearest picture of how I approach agentic AI.

### 1. [agentic-physics-bench](https://github.com/retinapeg/agentic-physics-bench)

When does a model use a tool it is offered? V1 surprised me: Claude (in Claude Code) answered every least-squares slope task correctly and never requested the optional fitting tool, a ceiling result.

So for V2 I set a new question and three conditions: no, optional or required tool, across three difficulty levels. Correctness stayed at ceiling, but the model now always requested the optional tool. V2 does not isolate why: the CLI version, a prompt clause, the advisor setting and turn structure also changed.

Trace review caught tools-off development calls consulting a second model through the CLI's advisor; those runs were excluded and scored calls are checked. Claude Code wrote the code and ran the frozen batches; I approved every protocol before it ran.

Evidence (live, one model, synthetic tasks): V1: tool requested 0/12 · V2: 162 episodes, 54/54 correct per condition, optional tool requested 54/54 · 90 offline tests in CI

### 2. [agent-workflow-orchestrator](https://github.com/retinapeg/agent-workflow-orchestrator)

Codex and Claude take the same coding task in separate Git worktrees, cross-review diffs and revise in bounded rounds. Hard gates in code decide eligibility; only an explicit `integrate` touches the source repo.

Evidence: 150 offline tests (scripted providers), strict mypy · one self-reported live run (n=1, VALIDATION.md): Codex's review caught a Unicode edge case that Claude fixed

### 3. [YLOOKUP](https://github.com/retinapeg/YLOOKUP) · FundOps Control Room

Extracts page-cited fields from fictional capital-call notices, reconciles them with `Decimal` rules, queues breaks for a human and logs decisions append-only. Design rule: a model may read the notice; code does the arithmetic and a person clears every break. Coding agents built it to my rules.

Evidence (synthetic fixture, rule-based path, no model calls): 27 cases, 4/4 gates pass · 150 tests in CI · model mode unevaluated

### 4. [agent-context-router](https://github.com/retinapeg/agent-context-router)

A fresh agent session picks a route and note; code returns a capped, sha256-cited packet and refuses edits against a stale hash. Claude Code wrote it to my specification. Main result: a keyword-matching stand-in for the agent loses to BM25; real-model route choice is unmeasured.

Evidence (offline, 41 hand-labelled requests, synthetic notes, no model calls): stand-in 21/31 vs BM25 top-1 24/31 on routable requests · live: two fresh Claude Code sessions recovered a note with the correct hash; no-tool controls could not

## What these projects have in common

- Behaviour, not just answers: which tool the model called, what it relayed, where it broke.
- Bounded autonomy: models propose; code and people decide.
- Measured iteration: frozen protocols and baselines; ceilings and losses reported.
- Software that survives inspection: saved traces, hashes, append-only logs, offline tests.

## More work

- [Role-prompting pilot](https://github.com/retinapeg/institutional-workbench/tree/v0.3-benchmark-lab/benchmarks/results) (institutional-workbench, branch `v0.3-benchmark-lab`): 96 calls, Claude and Codex CLIs, synthetic tasks. No specialist-role benefit was established, and 33 of 96 calls failed at the protocol layer, mostly Markdown-fenced JSON and timeouts.
- [fleetcast](https://github.com/retinapeg/fleetcast): NYC taxi-pickup forecasting on public data; boosted trees beat persistence on a chronological holdout (MAE 10.83 vs 14.29). No LLM.
- [dronewatch](https://github.com/retinapeg/dronewatch): Kalman multi-target tracking through sensor dropouts on synthetic data; NEES/NIS consistency checks, failure cases reported.
- [institutional-ai](https://github.com/retinapeg/institutional-ai): specialist-agent prototype (peer challenge, preserved dissent, hash-linked audit log) on a deterministic demo provider; no model calls yet.

## Stack

Python (NumPy, pandas, scikit-learn, DuckDB), Pydantic, FastAPI, Streamlit, SQLite · pytest, mypy, ruff, GitHub Actions · Claude Code, Codex, MCP
