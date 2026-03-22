# The Art of Action — From Intent to Outcome

A lightweight, domain-agnostic framework for turning intent into verifiable outcomes —
without collapsing into bureaucracy or drifting into undirected activity.

---

## Background

This framework is inspired by Stephen Bungay's *The Art of Action* and the principle of
mission-based leadership: give the intent, not the procedure. The real challenge is not
to eliminate uncertainty, but to act effectively within it.

Bungay identifies three gaps that consistently appear between intention and outcome:

| Gap | What it is |
|---|---|
| **Knowledge Gap** | The difference between what you know and what you need to know to decide |
| **Alignment Gap** | The difference between what you intend and what your agents understand |
| **Effects Gap** | The difference between what you expect to happen and what actually happens |

Traditional approaches try to close these gaps by demanding more information upfront,
writing more detailed plans, or tightening control over execution. This framework takes
the opposite approach: make the gaps visible at each step, so that human judgement can
close them deliberately — before they become failures.

---

## How It Works

The process is milestone-driven. Each milestone follows a two-phase loop.

Before any action is taken, the agent authors a Milestone Backbrief: for each Concrete
Step, it classifies its basis as CONFIRMED, INFERRED, or ASSUMED, and states the
consequence if wrong. Invisible assumptions become visible choices — reviewable before
execution begins. This closes the Knowledge and Alignment Gaps.

Then the agent executes. Decisions, discoveries, and blockers are recorded in the plan
file as they occur. After all steps are complete, the agent writes a Milestone Audit:
a verdict per acceptance criterion (PASS with evidence, FAIL with a required follow-up,
or UNVERIFIED with a reason why closing is still acceptable), then marks the milestone
[CLOSED]. This closes the Effects Gap.

Every decision made during execution is recorded in the Decision Log. Closed milestones
are immutable. The plan stays current with the actual state of the work and must always
be restartable from the file alone. This keeps the Alignment Gap closed continuously.

The goal is not to follow the process. The goal is to achieve the outcome.

---

## Setup

Place `execution-plan-instructions.md` at `.agents/execution-plan-instructions.md` and
add this to your agent configuration file (`AGENTS.md`, `CLAUDE.md`, or
`.github/copilot-instructions.md`):

    ## ExecutionPlan

    When working on any complex or multi-step task, use an ExecutionPlan as described
    in `.agents/execution-plan-instructions.md` — read that file in full before starting,
    and again if your context has been reset.

Then create `your-plan.md` for the specific piece of work, using the skeleton in
`execution-plan-instructions.md` as the starting point. One file per task.
