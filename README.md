# Leo Aarons-Ditson

Theoretical Physics (UCL) · London · looking for AI engineering and data science roles

I build AI and data systems that are tested and evaluated, and I write down what they don't show. I treat model output as a proposal: it's grounded against evidence, validated against a schema and checked deterministically before anything relies on it.

**How I work with AI:** I frame the problem, design the evaluations and acceptance checks, and review every change. Claude Code and Codex write much of the implementation. Each repo says how it was built.

### Start here

| Project | What it is | Result |
|---|---|---|
| [fleetcast](https://github.com/retinapeg/fleetcast) | 30-minute NYC taxi demand forecasting | Poisson gradient-boosted trees beat persistence on a chronological holdout: MAE 10.83 vs 14.29 |
| [FundOps Control Room](https://github.com/retinapeg/YLOOKUP) | Capital-call reconciliation with LLM extraction | A field is kept only if its quoted evidence is on the cited page. 27-case fixture eval: 267/270 fields exact, 12/12 exceptions caught |
| [agent-workflow-orchestrator](https://github.com/retinapeg/agent-workflow-orchestrator) | Claude and Codex solve the same task in isolated Git worktrees and review each other | Deterministic scoring picks the winner; 150 offline tests |

**Also:** [support-triage-agent](https://github.com/retinapeg/support-triage-agent) (bounded tool-using agent on validated structured outputs) · [dronewatch](https://github.com/retinapeg/dronewatch) (Kalman tracking; 0.99 ellipse coverage through a 15 s radar outage) · [uk-orbit-guard](https://github.com/retinapeg/uk-orbit-guard) (satellite collision avoidance, cross-entropy-method policy search) · [schrodinger-harmonic-demo](https://github.com/retinapeg/schrodinger-harmonic-demo) (finite-difference solver with an O(h²) convergence study)

**Stack:** Python, NumPy/SciPy, pandas, scikit-learn, PyTorch, Pydantic, FastAPI, Streamlit, pytest, mypy, GitHub Actions · Claude Code, Codex, OpenAI and Anthropic APIs
