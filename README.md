# Leo Aarons-Ditson

UCL-trained physicist (BSc, PGCert with Distinction) · London · [CV](./Leonard_Aarons-Ditson_CV.pdf)

I build agentic AI systems and then test whether they can be trusted. The pattern across my recent work: build the system, evaluate it, read the traces when the headline score looks too good, diagnose what failed, add controls, and measure whether the controls actually help. Negative results stay in the write-up.

## Featured work

The numbers below are the committed counts; each linked README has an evidence table pointing at the files that hold them.

### [agentic-physics-bench](https://github.com/retinapeg/agentic-physics-bench) · completed, frozen

Does an offered tool change how a model solves a problem, and can the trace prove that the system scored was the system declared? Correctness hit the ceiling in every condition (54/54 × 3), so the score said nothing. A per-call trace audit then found that a server-side advisor that consults a second model had been active in 31 of 48 development calls made with the CLI's tools switched off. Those stages were voided, the pathway was disabled, per-call model-identity checks were added, and all 324 held-out calls came back clean. Correct outputs alone did not prove that the declared system was the one being evaluated.

### [agent_reliability_lab](https://github.com/retinapeg/agent_reliability_lab) · first run complete

Does an independent model review catch coding defects that deterministic tests miss, and what does that cost? On 12 tasks, every generated solution passed its visible tests and 2 still failed hidden tests. A separate reviewer flagged both, plus one flag the hidden tests could not confirm; one bounded revision per flag fixed one of the two confirmed defects, and the other returned byte-identical code. Review took 1.36× the coding time. In this one run the oversight caught what the tests missed and also had its own cost and failure modes, which is why it is measured rather than assumed.

### [agent-failure-analysis](https://github.com/retinapeg/agent-failure-analysis) · v0.1.1 release candidate

Give it a recorded agent run plus the task and success criteria; get back an evidence-linked account of what happened, what is established, what is still a hypothesis, what evidence is missing and what regression test to add. Deterministic code verifies that every cited excerpt exists in the trace; the model interprets; the checker says in print that it does not verify the interpretation. Evaluated on synthetic traces only, and labelled as such.

### [institutional-workbench](https://github.com/retinapeg/institutional-workbench) · prototype, negative result kept

Claude and Codex take a small repo change from assessment to tested patch; does giving each model an expert role make it a better specialist? In a predeclared 96-call experiment, 33 calls failed on timeouts, provider errors or malformed output, all on the Claude Code CLI side (Codex 0/48), and 14 of the 16 malformed answers were JSON wrapped in Markdown fences. Almost all of the role prompts' apparent gain came from fewer format and completion failures; on schema-valid answers the three conditions were within 0.06 of each other, so no reasoning benefit was established. Protocol robustness dominated specialisation.

## Also

- [agent-context-router](https://github.com/retinapeg/agent-context-router): bounded context loading for agent sessions with hash-checked edits. The keyword picker lost to plain BM25 (21/31 vs 24/31), and the README says so.
- [careerops-ai](https://github.com/retinapeg/careerops-ai): a durable, graph-controlled CV workflow where Python owns state and transitions, models return bounded structured proposals, and independent red/blue reviews feed a bounded revision loop. No autonomous submission.
- [agent-workflow-orchestrator](https://github.com/retinapeg/agent-workflow-orchestrator): Codex and Claude build the same task and review each other's diffs; one recorded contest in which a review caught a Unicode bug.
- [institutional-ai](https://github.com/retinapeg/institutional-ai): AI specialists report independently, challenge each other and keep dissent on the record. Frozen prototype with scripted agent replies; no model is called.
- [fleetcast](https://github.com/retinapeg/fleetcast): NYC taxi-pickup forecasting; boosted trees cut MAE by 24% against persistence on a held-out fortnight.

Earlier and smaller: [dronewatch](https://github.com/retinapeg/dronewatch) · [YLOOKUP](https://github.com/retinapeg/YLOOKUP) · [before-coffee](https://github.com/retinapeg/before-coffee) · [support-triage-agent](https://github.com/retinapeg/support-triage-agent) · [canton-collateral-optimizer](https://github.com/retinapeg/canton-collateral-optimizer) · [uk-orbit-guard](https://github.com/retinapeg/uk-orbit-guard) · [schrodinger-harmonic-demo](https://github.com/retinapeg/schrodinger-harmonic-demo)

## How I work

Freeze the protocol before the scored run. Keep invalid episodes in the denominator, and keep voided runs on record. Treat each call's trace, not the aggregate score, as the primary evidence. Say what a result does not show.
