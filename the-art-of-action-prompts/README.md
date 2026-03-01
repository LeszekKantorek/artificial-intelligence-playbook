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

## Agents & Files

Each agent in this process is a prompt instruction file that defines how an AI (or human) should behave in a given mode. They are used sequentially and in combination.

| Agent | File | Role |
|---|---|---|
| **ExecutionPlan** | `execute-plan-instructions.md` | The living plan — captures intent, decisions, milestones, and acceptance criteria. Source of truth for the entire process. |
| **BackbriefPlan** | `backbrief-plan-instructions.md` | Audits the plan against source material *before* execution. Surfaces confirmed knowledge, inferences, and dangerous assumptions. |
| **AuditPlan** | `audit-plan-instructions.md` | Audits execution against the plan *after* each milestone. Verifies that actions are traceable to intent and that acceptance criteria are proven, not declared. |

---

## How to Use

The process is milestone-driven. Each milestone is intentionally small — it generates progress *and* evidence, and acts as a probe into the fog of uncertainty.

```
1.  Author the ExecutionPlan

2.  Run BackbriefPlan against ExecutionPlan + source documents
2a. Resolve open assumptions — update ExecutionPlan accordingly
2b. Repeat 2–2a until BackbriefPlan returns: READY FOR EXECUTION

3.  Execute Milestone 1
3a. Produce Milestone Report 1 — an immutable record of what actually happened, with evidence

4.  Run AuditPlan on Milestone Report 1
4a. Resolve unjustified actions and unverified acceptance criteria
4b. Repeat 4–4a until AuditPlan returns: MILESTONE CLOSED

5.  Run BackbriefPlan before the next milestone
5a. Update ExecutionPlan if context or intent has changed
5b. Repeat until READY FOR EXECUTION

6.  Execute next milestone → produce Milestone Report

7.  Run AuditPlan

    (Repeat steps 5–7 for each remaining milestone)

8.  Write Outcomes & Retrospective in ExecutionPlan
```

**A note on Milestone Reports:** a Milestone Report is not a plan. It is a record. Once written, it does not change — it captures what was done, what was found, and what evidence exists. The AuditPlan uses this record to verify alignment with the ExecutionPlan.

---

## Principles

Each step in the flow exists to close a specific gap before it becomes an error.

**BackbriefPlan closes the Knowledge Gap.** Before any execution begins, the BackbriefPlan audits the plan against its sources. It distinguishes between what is confirmed, what is inferred, and what is an assumption. If assumptions are dangerous or undocumented, the plan is updated before work starts.

**AuditPlan closes the Effects Gap.** After each milestone, the AuditPlan checks whether what was done is traceable to what was intended. It does not evaluate whether execution was elegant or optimal — it checks for coherence between intent and reality, and requires evidence rather than declarations.

**Updating the ExecutionPlan closes the Alignment Gap.** Between milestones, the ExecutionPlan is updated to reflect new decisions, discoveries, and changes in context. This keeps intent, state, and understanding consistent as work progresses — and prevents the plan from becoming a historical artifact disconnected from the work it is supposed to guide.

---

## Philosophy

This process does not eliminate friction. Friction is a property of complex environments, not a failure of planning. What the process does is make the gaps visible at each transition point — before execution, after each milestone, and between milestones — so that the people doing the work can close them with judgement rather than discovering them as failures.

The goal is not to follow the process. The goal is to achieve the outcome. The process is the means, not the end.
