# Leo Aarons-Ditson

**UCL-trained physicist building agentic systems, AI evaluations and reliable AI applications.**

BSc Physics and Postgraduate Certificate in Physics (Distinction), UCL · London

I turn quantitative and operational problems into working software, then evaluate where the systems succeed, fail, or should defer to deterministic methods. My current focus is tool-using agents, reproducible evaluation and structured specialist-agent workflows.

**Engineering approach:** I define the problem, architecture, evaluation criteria and acceptance checks, then review and test changes against them. I keep research and change logs for substantial projects so design decisions, failures and implementation changes remain inspectable.

### Start here

| Project | Research question / system | Evidence and current focus |
|---|---|---|
| [Agentic Physics Bench](https://github.com/retinapeg/agentic-physics-bench) | When does a frontier model use an available numerical tool, and how do tool policy and task difficulty affect reliability? Claude via Claude Code, with a bounded line-fit tool. | **V1 (v1.0.0):** 12 held-out cases, both conditions 12/12, optional tool never requested (ceiling effect).<br>**V2 (v2.0.0):** 162 scored episodes across no-tool, optional-tool and required-tool conditions; final answers 54/54 in each; optional tool requested 54/54 (V1: 0/12). Frozen protocols, deterministic grading, every episode saved; the design does not isolate why uptake changed. |
| [Institutional AI \| Specialist-Agent Research](https://github.com/retinapeg/institutional-ai) | Do expert-role prompts improve performance on objectively scored specialist tasks compared with neutral prompting? | **Built:** specialist-agent prototype with independent reports, typed communication, peer challenge, preserved dissent and a hash-linked audit log. Reasoning is currently a deterministic demo provider (no model calls).<br>**Next experiment (planned, not run):** expert-role vs neutral prompts with the same model, task information, tools and inference budget, separating persona wording from extra agents, context or review rounds. |
| [FundOps Control Room](https://github.com/retinapeg/YLOOKUP) | Evidence-grounded extraction from capital-call notices, deterministic reconciliation, review and audit trail | In model mode, extracted fields are kept only if their quoted evidence is on the cited page; `Decimal` controls; append-only decision log. Deterministic-path eval on 27 synthetic cases (0 model calls): 267/270 fields exact, 4/4 regression gates; 150 tests. |
| [Agent Workflow Orchestrator](https://github.com/retinapeg/agent-workflow-orchestrator) | Bounded coding-agent workflows: Codex and Claude take the same task in isolated Git worktrees, then cross-review and revise | Candidates are re-checked in a fresh checkout against explicit acceptance gates and scored deterministically; nothing touches the source checkout without `integrate`. 150 offline tests, strict mypy; one live Codex-vs-Claude run documented. |

### More work

- [fleetcast](https://github.com/retinapeg/fleetcast): 30-minute NYC yellow-taxi pickup forecasting; Poisson gradient-boosted trees beat persistence on a chronological holdout (MAE 10.83 vs 14.29).
- [dronewatch](https://github.com/retinapeg/dronewatch): Kalman tracking with chi-squared gating and NEES/NIS evaluation on synthetic sensor data.
- [support-triage-agent](https://github.com/retinapeg/support-triage-agent): bounded tool-using support agent on validated structured outputs.
- [uk-orbit-guard](https://github.com/retinapeg/uk-orbit-guard): hackathon prototype; cross-entropy-method policy search on synthetic satellite-encounter scenarios.
- [schrodinger-harmonic-demo](https://github.com/retinapeg/schrodinger-harmonic-demo): finite-difference solver with an O(h²) convergence study.

**Stack:** Python, NumPy/SciPy, pandas, scikit-learn, Pydantic, FastAPI, Streamlit, pytest, mypy, GitHub Actions · Claude Code, Codex, OpenAI and Anthropic APIs
