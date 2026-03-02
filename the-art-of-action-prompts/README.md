# The Art of Action — From Intent to Outcome

A lightweight, domain-agnostic framework for turning intent into verifiable outcomes — without collapsing into bureaucracy or drifting into undirected activity.

---

## Background

This framework is inspired by Stephen Bungay's *The Art of Action* and the Prussian military doctrine of *Auftragstaktik* (mission-based leadership). Bungay's central argument is that in complex, unpredictable environments, detailed plans create a false sense of certainty. The real challenge is not to eliminate uncertainty, but to act effectively within it.

Bungay identifies three gaps that consistently appear between intention and outcome:

| Gap | What it is |
|---|---|
| **Knowledge Gap** | The difference between what you know and what you need to know to decide |
| **Alignment Gap** | The difference between what you intend and what your agents understand |
| **Effects Gap** | The difference between what you expect to happen and what actually happens |

Traditional approaches try to close these gaps by demanding more information upfront, writing more detailed plans, or tightening control over execution. This framework takes the opposite approach: make the gaps visible at each step, so that human judgement can close them deliberately — before they become failures.

---

## How to Use

The process is milestone-driven. Each milestone follows the same three-phase loop.

    1. Author the ExecutionPlan using execution-plan-instructions.md

    For each milestone:

    2. Milestone Backbrief — written to the conversation before touching anything.
       States what will be done and on what basis (CONFIRMED / INFERRED / ASSUMED).

    3. Milestone Execution — execute the Concrete Steps in order.
       Record decisions, discoveries, and blockers in the plan file as they occur.

    4. Milestone Audit — written to the conversation after all steps are complete.
       Classifies each action (JUSTIFIED / UNJUSTIFIED / UNVERIFIED).
       Updates the plan: milestone status → [CLOSED], living sections updated.

    5. Proceed to the next [OPEN] milestone. Repeat steps 2–4.

    6. When all milestones are [CLOSED], write Outcomes & Retrospective.

Milestone Backbrief and Milestone Audit are informational outputs — they do not block or gate execution. The principal reads them and decides whether to continue.

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

## Why It Works

This process does not eliminate friction. Friction is a property of complex environments, not a failure of planning. What it does is make the three gaps visible at the right moment — so they can be closed with judgement before they become failures.

**Milestone Backbrief closes the Knowledge Gap.** Before any action is taken, the agent states what it understands, what it is inferring, and what it is assuming. Invisible assumptions become visible choices.

**Milestone Audit closes the Effects Gap.** After each milestone, the agent accounts for every action: whether it was directed by the plan, and whether acceptance criteria have evidence. Intent and reality are checked against each other — not optimism.

**Updating the ExecutionPlan closes the Alignment Gap.** Every decision made during execution is recorded. The plan stays current with the actual state of the work. It must always be possible to restart from the file alone.

The goal is not to follow the process. The goal is to achieve the outcome. The process is the means, not the end.
