# Execution Plan (ExecutionPlan)

An ExecutionPlan is a self-contained executable specification that an AI agent follows
to deliver a defined outcome. It contains all knowledge, context, constraints, and
instructions the agent needs — no external context is assumed. If a fact, rule, or
decision matters, it must be stated here or listed under Reference Materials.

An ExecutionPlan is a living document. The file is the single source of truth for the
state of the work at any point in time. Milestone statuses, decisions, discoveries,
and audit results are recorded here as work proceeds.


## How to Use an ExecutionPlan

**When authoring:** start from the skeleton, embed the domain knowledge the executor needs,
and resolve ambiguities inside the plan. For each Concrete Step, complete Phase 1 —
Authoring as defined in Executing a Milestone. Unknowns that cannot be resolved go to
Open Questions.

**When executing:** read the entire plan before acting. Follow the two-phase loop in
Executing a Milestone. Keep living sections current. Any conclusion left only in chat
history is treated as lost.

**When updating:** record every meaningful change in the Decision Log. The plan must
remain restartable from the file alone at any point.


## Executing a Milestone

Every milestone follows two phases: Authoring closes the Knowledge and Alignment Gaps
before action; Execution closes the Effects Gap and verifies Alignment after.


### Phase 1 — Authoring

Read the full ExecutionPlan. For each Concrete Step in the milestone, write inline
under each step — meaning on the immediately following indented bullet lines, with
no blank line between the step and its bullets:

- `Outcome:` what success looks like; known failure conditions if any.
- `Basis:` classify and support the action:

        CONFIRMED — directly stated in the ExecutionPlan or a named Reference Material;
                    provide a verbatim quote or section reference, not a paraphrase
        INFERRED  — consistent with the plan but not stated directly; explain the reasoning
        ASSUMED   — no basis in the plan; state what is unknown and what is taken as fact

- `Risk:` required for INFERRED and ASSUMED; state the consequence if the basis
  proves incorrect. May be omitted for CONFIRMED.

The completed steps constitute the Milestone Backbrief. Once execution begins, they may
only be edited if the underlying Concrete Step has changed — any such change must be
recorded in the Decision Log.


### Phase 2 — Execution

Execute the Concrete Steps in order, observing outcomes against each step's expected result.

Record unexpected findings in Surprises and Discoveries as they occur. If an unplanned
decision becomes necessary, record it in the Decision Log with rationale and alternatives,
then update affected plan sections. Resolved Open Questions move to Decision Log or
Surprises and Discoveries.

If a step fails unexpectedly, record the failure and decision in the Decision Log and
continue. If the milestone becomes uncompletable, record the blocker in Open Questions
and stop.

After all steps are complete, write the Milestone Audit to Outcomes and Retrospective.
For each acceptance criterion state the verdict — PASS with attached evidence as
sub-bullets, FAIL with a required Decision Log entry or Open Question, or UNVERIFIED
with an explanation of what is missing and why closing is still acceptable. Precede
the criteria with a brief prose summary of what was achieved plus bullet points for
notable achievements, then Deviations and Issues discovered as inline "none" or
bullet lists. Use the template in Outcomes and Retrospective.

Then update the plan:
- milestone heading status → [CLOSED YYYY-MM-DD HH:MMZ]
- Open Questions → remove resolved entries
- Decision Log → ensure all execution decisions are recorded

Proceed to the next [OPEN] milestone.


## Requirements

**The ExecutionPlan must be fully self-contained.** No external context is assumed.
Anything outside the plan must be listed under Reference Materials; anything not listed
there is treated as unavailable.

**Closed milestones are immutable.** Once a milestone is marked [CLOSED], its description,
Acceptance criteria, and Concrete Steps must not be edited. The only permitted writes after
closing are additions to Decision Log, Surprises and Discoveries, and Outcomes and
Retrospective. Editing a closed milestone's content is a plan violation equivalent to
falsifying evidence. When an unplanned decision requires updating affected plan sections,
only open milestones and living sections may be changed — closed milestone content is
never updated regardless of what is discovered later.

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

Write the ExecutionPlan as plain Markdown. Use prose by default; lists when naming
discrete items or when structure aids scanning. Concrete Steps are numbered lines;
each step carries sub-bullet fields for Outcome, Basis, and Risk — on the lines
immediately following the step, no blank line between them. No fenced code blocks;
use four-space indented blocks for excerpts and snippets.

Heading levels: `#` plan title, `##` top-level sections, `###` milestones and
milestone audits. Do not go deeper than `###`. Do not rename, reorder, or merge
sections.


## ExecutionPlan Skeleton

    # <Short, action-oriented description of the work>

    This ExecutionPlan is a living document. Decision Log, Open Questions, Surprises and
    Discoveries, and Outcomes and Retrospective are kept at the end of the file and must
    be updated as work proceeds. Milestone status is tracked in each milestone heading.

    This plan is governed by execution-plan-instructions.md. If that file is not in your
    context, read it in full before proceeding.


    ## Intentions

    Describe the desired end-state and why it matters. What will be true when this work
    is done, and why that outcome is worth pursuing. Two to four sentences.


    ## Alignment and Autonomy

    Name the part of the work that, if it fails, makes everything else irrelevant. Then
    state what must not be done, what is forbidden, what must not be compromised, and what is out of scope. Include anti-goals. 

    Autonomy: 
    - <name areas where initiative and independent judgement are expected — approach, tooling 
      implementation order, error handling, and anything else the executor should own without asking.>


    ## Context

    Describe the current state of the domain or workspace as if the reader knows nothing.
    Name the key resources, systems, roles, and locations. Define non-obvious terms at the
    point of use.


    ## Reference Materials

    - Reference-1: `<path or name>`
      - <why it matters and how it will be used>
      - <second point if needed>
    - Reference-2: `<path or name>` [MISSING — recorded in Open Questions]
      - <why it matters and how it will be used>


    ## Deliverables and Dependencies

    - Deliverable-1: <name every artifact this plan must produce with enough specificity
      that a reviewer can confirm it exists and is correct without asking anyone>
    - Deliverable-2: <...>

    - Dependency-1: <every external requirement the deliverables must satisfy or integrate
      with; do not list reference materials here>
    - Dependency-2: <...>


    ## Plan of Work

    1. <What to establish first and why this must come before everything else.>
    2. <What to build next and why this order makes sense given what came before.>
    3. <What to finish last and why this belongs at the end.>


    ## Milestones

    Status markers:

        [OPEN]                       — not yet closed
        [CLOSED YYYY-MM-DD HH:MMZ]   — closed after Milestone Audit


    ### Milestone 1 — <title> [OPEN]

    A short paragraph: how this milestone advances the overall Intentions. What will
    exist at the end that did not exist before, what work produces it, and what the
    executor must demonstrate to consider it closed.

    Acceptance criteria:
    - <Observable outcome, not internal state. State what evidence will prove this
      criterion — a file path, test name, command output, or observable artifact.>
    - <Observable outcome, not internal state. State what evidence will prove this
      criterion — a file path, test name, command output, or observable artifact.>

    Concrete Steps:

    1. <What to do and where — one line.>
       - Outcome: <what success looks like; known failure conditions if any.>
       - Basis: CONFIRMED — "<verbatim quote or section reference>"
       - Risk: n/a

    2. <What to do and where — one line.>
       - Outcome: <what success looks like; known failure conditions if any.>
       - Basis: INFERRED — <reasoning: why this follows from the plan even though not stated>
       - Risk: <consequence if the inference is wrong>

    3. <What to do and where — one line.>
       - Outcome: <what success looks like; known failure conditions if any.>
       - Basis: ASSUMED — <what is unknown and what is taken as fact>
       - Risk: <consequence if the assumption is wrong>


    ### Milestone 2 — <title> [OPEN]

    …

    Acceptance criteria:
    - <Observable outcome. State what evidence will prove this criterion.>

    Concrete Steps:

    1. <What to do and where — one line.>
       - Outcome: <what success looks like.>
       - Basis: CONFIRMED / INFERRED / ASSUMED — <support>
       - Risk: <consequence, or n/a for CONFIRMED>


    ## Validation and Acceptance

    Describe how to verify that the work as a whole is complete — the end-to-end check
    that confirms all milestones together delivered the intended outcome.


    ## Reversibility and Recovery

    State whether steps can be safely repeated. Identify risky or irreversible steps and
    provide recovery paths.


    ---


    ## Decision Log

    - Decision: …
      - Rationale: …
      - Alternatives: …
      - Sections updated: …


    ## Open Questions

    - Question: …
      - Resolved by: …
      - Blocks: …


    ## Surprises and Discoveries

    - Observation: …
      - Evidence: …
      - Milestone: …


    ## Outcomes and Retrospective

    Written after each milestone closes and again at the end of the full plan.


    ### Milestone Audit — Milestone N: [title]

    <One to two sentences on what was achieved overall.>
    - <main achievement worth mentioning>
    - <second achievement worth mentioning>

    Deviations: none

    Issues discovered: none

    Acceptance criteria results:

    - PASS: <Criterion text from Milestone N>
      - <log output / file path / observable artifact / user confirmation>
      - <second piece of evidence if needed>

    - FAIL: <Criterion text from Milestone N>
      - <what was observed>
      - Action taken: <Decision Log entry date / Open Question added>

    - UNVERIFIED: <Criterion text from Milestone N>
      - Missing: <what evidence would prove this criterion>
      - Why acceptable: <why the milestone may close without this evidence>


    ### Plan Retrospective

    Written once, after the final milestone closes.

    <Restate the intention in one sentence.>

    Achieved:
    - <...>
    - <...>

    Not achieved: none

    Key learnings:
    - <...>
    - <...>
