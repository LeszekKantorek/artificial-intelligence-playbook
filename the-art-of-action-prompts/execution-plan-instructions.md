# Execution Plan (ExecutionPlan)

An ExecutionPlan is a self-contained executable specification that an AI agent follows
to deliver a defined outcome. It contains all knowledge, context, constraints, and
instructions the agent needs — no external context is assumed. If a fact, rule, or
decision matters, it must be stated here or listed under Reference Materials.

An ExecutionPlan is a living document. The file is the single source of truth for the
state of the work at any point in time. Milestone statuses, decisions, and discoveries
are recorded here as execution proceeds.

Milestone Backbrief and Milestone Audit are structured outputs written to the conversation —
one before execution begins, one after it ends. They have no file and leave no artifact.
Their format is defined in Executing a Milestone below.


## How to Use an ExecutionPlan

**When authoring:** start from the skeleton, embed the domain knowledge the executor needs,
and resolve ambiguities inside the plan. Unknowns that cannot be resolved go to Open
Questions with a milestone assigned to answer them.

**When executing:** read the entire plan before acting. Follow the three-phase loop in
Executing a Milestone. Keep living sections current. Any conclusion left only in chat
history is treated as lost.

**When updating:** record every meaningful change in the Decision Log. The plan must
remain restartable from the file alone at any point.


## Executing a Milestone

Every milestone follows the same three-phase loop: Milestone Backbrief, Milestone
Execution, Milestone Audit. Both Backbrief and Audit are informational outputs written
to the conversation in the same language as the plan — they do not block or gate anything.


### Phase 1 — Milestone Backbrief

Read the full ExecutionPlan, then write to the conversation:

**Milestone Backbrief — Milestone N: [title]**

Intention as understood: restate the overall Intention and how this milestone contributes
to it. One to three sentences — a demonstration of understanding, not a copy-paste.

Constraints active for this milestone: list every boundary and anti-goal from Main Effort
and Boundaries that applies here. State what each one protects.

What will be done and on what basis: describe the planned actions and classify each:

    CONFIRMED — directly stated in the ExecutionPlan or a named Reference Material; cite the source
    INFERRED  — consistent with the plan but not stated directly; explain the reasoning
    ASSUMED   — no basis in the plan; state what is unknown and what is taken as fact


### Phase 2 — Milestone Execution

Execute the Concrete Steps in
the order written, observing outcomes against the expected results stated in each step.

Record unexpected findings in Surprises and Discoveries as they occur. If a decision not
covered by the plan becomes necessary, record it immediately in the Decision Log with
rationale and alternatives considered, then update any affected plan sections. If an Open
Question is resolved, move the answer to Decision Log or Surprises and Discoveries.

If a step fails in a way the plan did not anticipate, record the failure, decide how to
proceed, record that decision in the Decision Log, and continue. If the milestone becomes
uncompletable without a plan change, record the blocker in Open Questions and stop.


### Phase 3 — Milestone Audit

Write to the conversation:

**Milestone Audit — Milestone N: [title]**

What was done and why — classify each significant action:

    JUSTIFIED   — directed by the ExecutionPlan or a Decision Log entry; cite the source
    UNJUSTIFIED — no traceable basis in the plan and no decision recorded explaining why
    UNVERIFIED  — an acceptance criterion has no corresponding evidence; state what is missing

Then update the plan:
- milestone heading status → [CLOSED YYYY-MM-DD HH:MMZ]
- Outcomes and Retrospective → brief comparison of what was achieved against the milestone's purpose
- Open Questions → remove resolved entries
- Decision Log → ensure all execution decisions are recorded

Proceed to the next [OPEN] milestone.


## Requirements

**The ExecutionPlan must be fully self-contained.** No external context is assumed.

**Anything outside the plan must be listed under Reference Materials.** Anything not
listed there is treated as unavailable.

**Every non-obvious term must be defined in place.** Not in a glossary — at the point of use.

**The four living sections — Decision Log, Open Questions, Surprises and Discoveries, and
Outcomes and Retrospective — are not optional.** They must reflect the actual current state
of the work at all times.

**Each milestone must state its acceptance criteria and the evidence that will prove them.**
If the work product is non-visible, define a concrete proxy a reviewer can inspect.

**Do not invent facts, sources, results, or decisions.** Anything uncertain goes to Open
Questions.

**Deviations are allowed only when recorded.** A deviation without a Decision Log entry
is a plan violation, not an exercise of judgement.

**Missing reference materials are blockers.** Record in Open Questions and stop until
available or replaced by an exploratory milestone.


## File Format

Write the ExecutionPlan as plain Markdown. Use prose by default; lists only when naming
discrete items. Concrete Steps are numbered prose paragraphs — no sub-bullets. No fenced
code blocks; use four-space indented blocks for excerpts and snippets.

Heading levels: `#` plan title, `##` top-level sections, `###` milestones. Do not go
deeper than `###`. Do not rename, reorder, or merge sections.


## ExecutionPlan Skeleton

    # <Short, action-oriented description of the work>

    This ExecutionPlan is a living document. Decision Log, Open Questions, Surprises and
    Discoveries, and Outcomes and Retrospective are kept at the end of the file and must
    be updated as work proceeds. Milestone status is tracked in each milestone heading.

    This plan is governed by execution-plan-instructions.md. If that file is not in your
    context, read it in full before proceeding.


    ## Intention

    What must be true when this work is done, and why it matters. Two to four sentences.
    Describe the desired end-state and its purpose — not the tasks or outputs that produce it.


    ## Main Effort and Boundaries

    Name the part of the work that, if it fails, makes everything else irrelevant. Then
    state what must not be done, what must not be compromised, and what is out of scope.
    Include anti-goals.


    ## Context and Orientation

    Describe the current state of the domain or workspace as if the reader knows nothing.
    Name the key resources, systems, roles, and locations. Define non-obvious terms at the
    point of use — not here as a glossary.


    ## Reference Materials

    - <n>: <why it matters and how it will be used>
    - <n>: <why it matters and how it will be used> [MISSING — recorded in Open Questions]


    ## Deliverables and Dependencies

    Deliverables: name every artifact this plan must produce with enough specificity that
    a reviewer can confirm it exists and is correct without asking anyone.

    Dependencies: name every external requirement the deliverables must satisfy or integrate
    with. Do not list reference materials here.


    ## Plan of Work

    A short narrative of the full sequence: what happens in what order and why that order
    makes sense. This is not a task list — it is an explanation of the strategy.


    ## Milestones

    Status markers:

        [OPEN]                       — not yet closed
        [CLOSED YYYY-MM-DD HH:MMZ]   — closed after Milestone Audit


    ### Milestone 1 — <title> [OPEN]

    A short paragraph: what will exist at the end that did not exist before, what work
    produces it, and what the executor must demonstrate to consider it closed.

    Acceptance criteria:
    - <Observable outcome, not internal state.>
    - <Observable outcome, not internal state.>

    Concrete Steps:

    1. <What to do and where. Expected outcome: what success looks like. If the step
       depends on a condition or can fail in a known way, describe it here.>

    2. <Next step. Expected outcome: what to observe to confirm it worked.>


    ### Milestone 2 — <title> [OPEN]

    …

    Acceptance criteria:
    - <Observable outcome.>

    Concrete Steps:

    1. …


    ## Validation and Acceptance

    Describe how to verify that the work as a whole is complete — the end-to-end check
    that confirms all milestones together delivered the intended outcome.


    ## Reversibility and Recovery

    State whether steps can be safely repeated. Identify risky or irreversible steps and
    provide recovery paths.


    ---


    ## Decision Log

    - Decision: …
      Rationale: …
      Alternatives considered: …
      Sections updated: …
      Date/Author: …


    ## Open Questions

    - Question: …
      Resolved by: …
      Blocks: …


    ## Surprises and Discoveries

    - Observation: …
      Evidence: …
      Milestone: …


    ## Outcomes and Retrospective

    Written after each milestone closes and at the end of the full plan.
    Compare what was achieved against the Intention. State what remains open and what
    was learned.
