# Leo Aarons-Ditson

UCL-trained physicist (BSc, PGCert with Distinction) · London · laaronsditson@gmail.com · [CV (PDF)](./Leonard_Aarons-Ditson_CV.pdf) · [LinkedIn](https://www.linkedin.com/in/leonardthomasaaronsditson)

Open to Data Scientist, AI Engineer, Forward Deployed Engineer and Evals / Research Engineer roles in London.

I build agentic AI systems and then test whether they can be trusted. The pattern across my recent work: build the system, evaluate it, read the traces when the headline score looks too good, diagnose what failed, add controls, and measure whether the controls actually help. Negative results stay in the write-up.

## Recent

### [Mathematical-proof-revamp](https://github.com/retinapeg/Mathematical-proof-revamp) · Reinvent the Wheel hackathon, 17 October 2026

Isabelle/HOL in stock VS Code, with an agent that writes proofs the kernel checks. A VS Code extension (goal state at the cursor, inline errors, a proof graph that turns green step by step as the kernel accepts them) and an MCP server exposing the live proof state so Claude Code or Codex can write a proof one step at a time. The agent proposes; only the kernel says proved. Built in one day; implementation solo, concept with Alex Hyman.

### Hackathon builds, 2026

- **Cantor8 "Build on Canton"**, August, lead engineer in a team of five: designed the maths and implemented the core of a linear-programming collateral optimiser with on-ledger contracts. $500 prize from the Canton-ecosystem judging panel; the team was admitted to Cantor8's investor accelerator. Code: [canton-collateral-optimizer](https://github.com/retinapeg/canton-collateral-optimizer).
- **Rebuild Private Markets (Ylookup × Encode)**, September, team of four: [YLOOKUP](https://github.com/retinapeg/YLOOKUP), page-cited extraction from fund documents scored against a labelled gold set, with deterministic arithmetic and a human clearing every break so the model never grades itself.
- **Daytona HackSprint (Entrepreneurs First)**, August, team build: a policy-gradient agent flying a spacecraft through a gravitational field on a purpose-built N-body simulator; diagnosed a zero-scoring policy and derived the braking reward term that fixed it. Later: [uk-orbit-guard](https://github.com/retinapeg/uk-orbit-guard).

## Featured work

The numbers below are the committed counts; each linked README has an evidence table pointing at the files that hold them.

### [partnerflow-lab](https://github.com/retinapeg/partnerflow-lab) · a partner lending channel you can break and measure

Two halves. Operations: a FastAPI lending API with partner keys, switchable faults, a faulty release and the monitoring that catches it, with a dashboard for the post-mortem. Experiments (`experiments/`): when a feature rolls out partner by partner and the biggest partners go first, how much of the measured lift is the feature? A simulated partner-referred lending funnel with the answer baked in (40 partners, 137,370 journeys; pre-qualification rolled out in an order correlated with partner size, +6 pp true effect on application completion, +2 pp on drawdown; a notification with a delayed 90-day outcome, +4 pp), and estimators tested against that truth. Naive before/after overstates the feature by about 4 points on both outcomes; two-way fixed-effects difference-in-differences lands within half a point (5.55 vs 6.00, 2.17 vs 2.00); the randomised A/B on the notification is unbiased (4.12 vs 4.00); a hierarchical Bayesian model's partner-level intervals cover 92.5% of the true rates. The results table is generated from the passing tests, not typed. Simulation only, with the staggered-adoption caveats on TWFE stated; endpoints for funnel, power and experiment read-outs.

### [fleetcast](https://github.com/retinapeg/fleetcast) · demand forecasting on real data

Where will demand be in the next half hour, by zone? 7.05M NYC taxi trips aggregated with DuckDB into a 20-zone, 30-minute panel and judged on a chronological holdout against persistence and weekly-naive baselines. A Poisson gradient-boosted model beat persistence by 24% on MAE across 13,440 held-out cells (10.83 vs 14.29; weekly-naive 16.22). Past-only features, leakage tests, 28 automated tests, a Streamlit app for error analysis. A small positive residual bias lined up with stale weekly lags; it is reported as an association, with the ablation that would settle it named rather than claimed.

### [agentic-physics-bench](https://github.com/retinapeg/agentic-physics-bench) · completed, frozen

Does an offered tool change how a model solves a problem, and can the trace prove that the system scored was the system declared? Correctness hit the ceiling in every condition (54/54 × 3), so the score said nothing. A per-call trace audit during development found that a server-side advisor that consults a second model had been active in 31 of the 48 unique calls across the two development stages run before it was disabled, all made with the CLI's tools switched off. Those two stages were voided, the pathway was disabled, per-call model-identity checks were added, and all 324 held-out calls came back clean. Correct outputs alone did not prove that the declared system was the one being evaluated.

### [agent_reliability_lab](https://github.com/retinapeg/agent_reliability_lab) · first run complete

Does an independent model review catch coding defects that deterministic tests miss, and what does that cost? On 12 tasks, every generated solution passed its visible tests and 2 still failed hidden tests. A separate reviewer flagged both, plus one flag the hidden tests could not confirm; one bounded revision per flag fixed one of the two confirmed defects, and the other returned byte-identical code. Review took 1.36× the coding time. In this one run the oversight caught what the tests missed and also had its own cost and failure modes, which is why it is measured rather than assumed.

### [institutional-workbench](https://github.com/retinapeg/institutional-workbench) · real effect or measurement artefact?

Claude and Codex take a small repo change from assessment to tested patch; does giving each model an expert role make it a better specialist? In a predeclared 96-call experiment, 33 calls failed on timeouts, provider errors or malformed output, all on one CLI side (the other 0/48), and 14 of the 16 malformed answers were JSON wrapped in Markdown fences. Almost all of the role prompts' apparent gain came from fewer format and completion failures; on schema-valid answers the three conditions were within 0.06 of each other, so no reasoning benefit was established. Protocol robustness dominated specialisation, and the gap was reported as a limit of the method, not a ranking.

### [agent-failure-analysis](https://github.com/retinapeg/agent-failure-analysis) · v0.1.1 release candidate

Give it a recorded agent run plus the task and success criteria; get back an evidence-linked account of what happened, what is established, what is still a hypothesis, what evidence is missing and what regression test to add. Deterministic code verifies that every cited excerpt exists in the trace; the model interprets; the checker says in print that it does not verify the interpretation. Evaluated on synthetic traces only, and labelled as such.

## Also

- [agent-workflow-orchestrator](https://github.com/retinapeg/agent-workflow-orchestrator): Codex and Claude build the same task in isolated worktrees and review each other's diffs against fresh acceptance checks; one recorded contest in which the review caught a Unicode defect that four passing tests missed.
- [agent-context-router](https://github.com/retinapeg/agent-context-router): bounded context loading for agent sessions with hash-checked edits. The keyword picker lost to plain BM25 (21/31 vs 24/31), and the README says so.
- [institutional-ai](https://github.com/retinapeg/institutional-ai): AI specialists report independently, challenge each other and keep dissent on the record. Frozen prototype with scripted agent replies; no model is called.
- [careerops-ai](https://github.com/retinapeg/careerops-ai): a graph-controlled analysis workflow where Python owns state and transitions, models return bounded structured proposals, and independent red/blue reviews feed a bounded revision loop; validators rejected unsupported claims in 151 of 251 first-pass plans.

Earlier and smaller: [dronewatch](https://github.com/retinapeg/dronewatch) · [before-coffee](https://github.com/retinapeg/before-coffee) · [support-triage-agent](https://github.com/retinapeg/support-triage-agent) · [schrodinger-harmonic-demo](https://github.com/retinapeg/schrodinger-harmonic-demo)

## How I work

Freeze the protocol before the scored run. Keep invalid episodes in the denominator, and keep voided runs on record. Treat each call's trace, not the aggregate score, as the primary evidence. Say what a result does not show.
