# The Art of Action — From Intent to Outcome

A lightweight, domain-agnostic framework for turning intent into verifiable outcomes — without collapsing into bureaucracy or drifting into undirected activity.

---

## Background

This framework is inspired by Stephen Bungay's *The Art of Action* and the principle of mission-based leadership: give the intent, not the procedure. The real challenge is not to eliminate uncertainty, but to act effectively within it.

Bungay identifies three gaps that consistently appear between intention and outcome:

| Gap | What it is |
|---|---|
| **Knowledge Gap** | The difference between what you know and what you need to know to decide |
| **Alignment Gap** | The difference between what you intend and what your agents understand |
| **Effects Gap** | The difference between what you expect to happen and what actually happens |

Traditional approaches try to close these gaps by demanding more information upfront, writing more detailed plans, or tightening control over execution. This framework takes the opposite approach: make the gaps visible at each step, so that human judgement can close them deliberately — before they become failures.

---

## How to Use

The process is milestone-driven. Each milestone follows a two-phase loop.

    1. Author the ExecutionPlan using execution-plan-instructions.md.

    For each milestone:

    2. Phase 1 — Authoring: for each Concrete Step, write inline the Basis
       (CONFIRMED / INFERRED / ASSUMED) and Risk if wrong. This constitutes
       the Milestone Backbrief — part of the plan file, written before any
       action is taken. The principal can review it before execution begins.

    3. Phase 2 — Execution: execute the Concrete Steps in order.
       Record decisions, discoveries, and blockers in the plan file as they occur.
       After all steps are complete, write the Milestone Audit to Outcomes and
       Retrospective: verdict per acceptance criterion (PASS / FAIL / UNVERIFIED),
       then mark the milestone [CLOSED].

    4. Proceed to the next [OPEN] milestone. Repeat steps 2–3.

    5. When all milestones are [CLOSED], write the Plan Retrospective.

---

## Getting Started

Two files. One snippet.

| File | Role |
|---|---|
| `execution-plan-instructions.md` | Instructions for authoring and executing an ExecutionPlan. Read this before creating or running any plan. |
| `your-plan.md` | The ExecutionPlan you create for a specific piece of work. One file per task. |

Place `execution-plan-instructions.md` at `.agents/execution-plan-instructions.md`, then add this to your agent configuration file (`AGENTS.md`, `CLAUDE.md`, or `.github/copilot-instructions.md`):

    ## ExecutionPlan

    When working on any complex or multi-step task, use an ExecutionPlan as described
    in `.agents/execution-plan-instructions.md` — read that file in full before starting,
    and again if your context has been reset.

---

## Closing the Gaps

This process does not eliminate friction. Friction is a property of complex environments, not a failure of planning. What it does is make the three gaps visible at the right moment — so they can be closed with judgement before they become failures.

**Milestone Backbrief closes the Knowledge and Alignment Gaps.** Before any action is taken, the agent classifies each step as CONFIRMED, INFERRED, or ASSUMED, and states the consequence if wrong. Invisible assumptions become visible choices — reviewable by the principal before execution begins.

**Milestone Audit closes the Effects Gap.** After each milestone, the agent accounts for every acceptance criterion: PASS with evidence, FAIL with a required follow-up action, or UNVERIFIED with an explanation of why closing is still acceptable. Intent and reality are checked against each other — not optimism.

**Updating the ExecutionPlan closes the Alignment Gap continuously.** Every decision made during execution is recorded in the Decision Log. Closed milestones are immutable. The plan stays current with the actual state of the work and must always be restartable from the file alone.

The goal is not to follow the process. The goal is to achieve the outcome. The process is the means, not the end.
