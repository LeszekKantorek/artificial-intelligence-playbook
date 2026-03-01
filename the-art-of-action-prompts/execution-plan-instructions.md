# Execution Plan (ExecutionPlan)

An ExecutionPlan is a self-contained executable specification that an AI agent follows to deliver a defined outcome. It provides all domain knowledge, constraints, and instructions the agent needs, assuming no memory of prior plans and no external context beyond what the plan includes or explicitly lists under Reference Materials. If a fact, rule, or decision matters, it must be stated here or listed under Reference Materials — treat anything else as unavailable. Keep it lean and testable: prefer short prose, explicit constraints, and acceptance criteria verified with evidence.

An ExecutionPlan works in conjunction with two companion documents: BackbriefPlan and AuditPlan. BackbriefPlan is executed before the first milestone begins — it verifies executor understanding before work starts. AuditPlan is executed after each Milestone Report — it verifies that what happened matches what the plan required.


## How to Use an ExecutionPlan

Use the ExecutionPlan as the shared reference across the whole lifecycle: shaping the work, executing it, and judging whether it is done.

**When authoring**, read these instructions in full before writing a single line. Start from the skeleton and fill it in while you research, embedding the domain knowledge the executor needs to make correct choices without hunting for context. Resolve ambiguities inside the plan — by defining terms, stating assumptions, or recording unknowns in Open Questions with a milestone assigned to answer each one. The plan is ready when an executor with no prior context can read it top to bottom, understand what matters, and know what evidence to produce.

**When updating**, treat the plan as a living contract that must stay restartable. Record meaningful changes as decisions so the next executor understands why the plan looks the way it does.

**When executing**, read the entire plan before acting and use the Intention and Boundaries as your compass for local judgement. Work milestone by milestone, keeping the living sections current and capturing evidence as you go. After each milestone: create the Milestone Report, run AuditPlan, and begin the next milestone only after receiving a MILESTONE CLOSED verdict. Do not stop to ask what to do next if the plan specifies a next milestone.

**When discussing**, anchor the conversation in Intention, Boundaries, and the next milestone. Any choice that changes scope, constraints, approach, or acceptance must be recorded in the plan — conclusions left only in chat history are treated as lost.

**When the work contains significant unknowns**, record them in Open Questions and design an exploratory milestone that produces a concrete artifact and evidence. Label it as exploratory and state the question it is intended to answer. When multiple unknowns are independent, explore them in separate milestones so a negative result in one does not contaminate the other.

**When backbriefing**, do not execute any work. Produce a Backbrief Report stating your understanding of the intention, the constraints and anti-goals you will operate within, any missing reference materials, and any assumption that could cause the work to fail. Execution must not begin until BackbriefPlan returns a READY FOR EXECUTION verdict.

**When auditing**, do not execute any work. Verify that actions are traceable to the plan, that acceptance criteria are demonstrated with evidence, and that deviations are recorded and justified. Execution of the next milestone must not begin until AuditPlan returns a MILESTONE CLOSED verdict.


## Requirements

**The ExecutionPlan must be fully self-contained** and must be kept self-contained through every revision. It must contain all knowledge, context, constraints, and instructions needed to execute the work. Anything the plan relies on outside itself must be explicitly listed under Reference Materials with a precise name, path, link, or identifier.

**Every non-obvious term must be defined at the point of use.** Do not collect definitions in a glossary — define a term in the same sentence or the next one where it first appears.

**The five living sections — Progress, Surprises and Discoveries, Decision Log, Open Questions, and Outcomes and Retrospective — are not optional** and must always reflect the actual current state of the work. If a conversation or decision changes intention, boundaries, milestones, definitions, or acceptance criteria, the plan must be revised immediately and the decision recorded. Anything left outside the plan is treated as lost.

**Each milestone must state its deliverables, acceptance criteria, and evidence that will be captured to prove them.** A milestone is not closed by assertion — the Milestone Report must contain evidence for every acceptance criterion, and AuditPlan must confirm that evidence before the next milestone begins.

**Do not invent facts, sources, results, measurements, or stakeholder decisions.** Anything uncertain must be an explicit assumption or an Open Question.

**Deviations are allowed only when made explicit.** Record a decision with rationale and alternatives considered, and update the plan. A deviation without a recorded decision is a plan violation.

**Missing reference materials are blockers.** If a listed reference material is missing, stop and record it in Open Questions. Do not bridge the gap with inference. If the missing information can be produced through direct exploration, add an exploratory milestone and record the decision. If it requires external input the executor cannot obtain autonomously, stop until it is resolved.

**Produce every artifact the plan promises and attach evidence for each acceptance criterion.** Outputs must be self-contained and reviewable without access to the conversation that produced them.


## File Format and Writing Style

Write the ExecutionPlan as plain Markdown with stable headings and short paragraphs. Use prose by default. Use lists only when naming discrete items where order or membership matters, and in the Progress section where checkboxes are required. Never use lists to describe behaviour, rationale, or sequence of thought in prose sections. Structured fields in living sections use labeled fields within list entries as defined in the skeleton. Concrete Steps within milestones are written as numbered prose paragraphs — each step is a separate paragraph beginning with its number, with context, conditions, and expected output written as additional sentences within that paragraph.

Do not use fenced code blocks anywhere in the plan. If a short excerpt, command, snippet, or diff must appear, use an indented block — four leading spaces. Put longer supporting source documents in separate files and list them under Reference Materials. Artifacts produced during execution belong in the Milestone Report as evidence, not in Reference Materials.

Use one blank line after every heading, and two blank lines between top-level sections. Heading levels: `#` for the plan title, `##` for top-level sections, `###` for milestones. Do not go deeper than `###`. Do not rename headings, reorder sections, or merge sections. Prefer appending to living sections over rewriting them. If you must refer to Markdown fences as a concept, write "triple backticks" rather than the characters.


## Guidelines

**Resolve ambiguity in the plan, not during execution.** When two interpretations are possible, choose one, explain why, and write the plan around that choice. If you cannot resolve an ambiguity before execution begins, record it in Open Questions and design a milestone to answer it.

**Write acceptance criteria from the perspective of someone who will use or inspect the result.** A criterion that is technically satisfied but delivers no real value is a plan failure. Ask: what does a correct outcome allow them to do or observe that an incorrect one does not?

**Do not outsource decisions to the executor.** When a trade-off exists, make it in the plan and record the rationale. An executor discovering a trade-off mid-execution will make choices without the context that shaped the plan, and those choices are invisible unless explicitly recorded — which cannot be assumed.

**Anchor every milestone in observable reality.** State what exists at the end of a milestone that did not exist before, and describe how a reviewer who was not present can confirm it. Vague outcomes produce unverifiable milestones.

**Capture evidence as you go, not after the fact.** Evidence reconstructed from memory after a milestone is complete is unreliable. A Milestone Report written from fresh evidence is the only kind AuditPlan can meaningfully verify.


## Intention

Every ExecutionPlan must contain an Intention section. It answers two questions: what must be true when this work is done (the desired end-state), and why it matters. It does not specify how — that freedom belongs to the executor within the Boundaries the plan defines. Keep it short enough to recall mid-execution and specific enough to resolve an unexpected choice.


## Main Effort and Boundaries

Every ExecutionPlan must identify the Main Effort: the part of the work that, if it fails, makes everything else irrelevant. When time or resources run short, the executor must know where to concentrate without asking.

Every ExecutionPlan must define Boundaries: what must not be done, what must not be compromised, and what falls outside scope. Include anti-goals — what this work is not trying to achieve — especially when a reader might reasonably assume otherwise.


## Milestones

A milestone describes a meaningful state change: what will exist at the end that did not exist before, what work produces it, and what evidence proves it. Write each milestone as a short paragraph stating purpose, work, result, and proof — in that order.

Each milestone must be independently verifiable. If the outcome of one milestone cannot be demonstrated without completing another, split them differently.

Each milestone contains a Concrete Steps block immediately after the acceptance criteria. Concrete Steps is a labeled prose block, not a heading. Each step is a separate prose paragraph beginning with its number; context, conditions, and expected output are further sentences within that paragraph — not sub-bullets or indented items. Completed steps are marked in Progress as checkboxes rather than deleted from Concrete Steps.

When a choice between approaches cannot be evaluated without trying them, parallel exploratory milestones are acceptable. Each must be labelled as exploratory, produce a concrete artifact or measurement, and state the criterion that determines which approach is promoted. A parallel milestone that produces no evidence capable of resolving the choice is not valid.

After completing each milestone, the executor must produce a Milestone Report before moving to the next milestone. A milestone is not considered closed until AuditPlan confirms the report contains the required evidence.


## Living Document Sections

**Progress** tracks granular steps as checkboxes. Every stopping point must be recorded here, including partially completed tasks — split into "done so far" and "remaining." Use timestamps to make pace of work visible.

**Surprises and Discoveries** captures anything unexpected: unanticipated constraints, behaviors differing from assumptions, or insights that changed the approach. Include concise evidence — an excerpt, a measurement, a concrete observation.

**Decision Log** records every material decision: what it was, why it was made, what alternatives were considered, when, and which plan sections were updated as a result. If no plan update was made, record why.

**Open Questions** records everything the plan cannot answer without external input or further exploration. Each entry must state the question precisely, identify who or what can resolve it, and name which milestone is blocked. When a question is answered, remove it and record the answer in Decision Log or Surprises and Discoveries as appropriate. The section must be empty by the time the final milestone begins; any remaining entry is a blocker.

**Outcomes and Retrospective** is written at the end of each milestone and at the end of the full plan. Compare what was achieved against the Intention. State what remains open and what was learned.


## Validation and Acceptance

Validation and Acceptance is the end-to-end check that confirms all milestones together delivered the intended outcome — not a repetition of per-milestone acceptance criteria. State the overall acceptance as observable behavior or indirect evidence: what a reviewer can do or observe to confirm the full intention was achieved.


## Reversibility and Recovery

State whether steps can be safely repeated. If a step is risky or difficult to undo, identify it explicitly and provide a recovery or rollback path. Prefer additive changes that preserve the ability to recover if a milestone's outcome is unsatisfactory.


## Reference Materials

Reference Materials is the allowlist of external sources the executor is permitted to read and rely on. Anything not listed here is treated as unavailable.

Each entry must name the source precisely enough that someone with no prior context can locate it: a file path, a URL, a document title with version, or a named deliverable. State why it matters and how it will be used. If a required source is not yet available, record it in Open Questions and mark it as missing here — it is a blocker unless a milestone is designed to produce or acquire it.


## Deliverables and Dependencies

**Deliverables** are the artifacts this plan must produce: documents, files, decisions, system states, or any other output a reviewer can inspect. Each must be named precisely enough that a reviewer can confirm it exists and is correct without asking anyone.

**Dependencies** are technical or external requirements the deliverables must satisfy — integrations, interfaces, services, or contracts the outputs must be compatible with. If a deliverable depends on something that does not yet exist, name that dependency and identify which milestone resolves it. Reference materials needed to write or execute the plan belong in Reference Materials, not here.


## Milestone Reports

Each Milestone Report is a separate file, not a section appended to the ExecutionPlan. Create it after completing each milestone, before moving to the next. A Milestone Report is complete only when all five required sections are present and no acceptance criterion is listed without evidence.

**Milestone Identity** — the milestone number, its title exactly as written in the ExecutionPlan, and the date and time of completion.

**Changes Made** — every artifact created, modified, or deleted: identified by path or name, with an explanation of what changed and why. Include full content or a concise diff for small artifacts; include only changed sections with surrounding context for larger ones.

**Steps Executed** — every significant action in the order it was taken: context, exact action, and observed outcome. If an action failed and was retried, record both the failure and the retry, and explain what changed between attempts.

**Decisions Made During Execution** — every decision not explicitly specified in the ExecutionPlan: what it was, what alternatives were considered, why this path was chosen, and which part of the plan's Intention or Boundaries guided the choice. If no unplanned decisions were made, state that explicitly.

**Acceptance Verification** — each acceptance criterion reproduced exactly as written in the ExecutionPlan, with a statement of whether it was met and the concrete evidence: the action taken, the output observed, the behavior demonstrated.


## ExecutionPlan Skeleton

The sections below are the required structure. Do not rename, reorder, or merge sections — the skeleton is fixed. What cannot be omitted: Intention, Main Effort and Boundaries, the five living sections, and the Milestone structure with its Reports.

    # <Short, action-oriented description of the work>

    This ExecutionPlan is a living document. Progress, Surprises and Discoveries, Decision Log,
    Open Questions, and Outcomes and Retrospective must be kept up to date as work proceeds.

    ## Intention

    What must be true when this work is done, and why it matters. Two to four sentences.
    Describe the desired end-state and its purpose — not the tasks or outputs that produce it.

    ## Main Effort and Boundaries

    Name the part of the work that, if it fails, makes everything else irrelevant. Then state
    what must not be done, what must not be compromised, and what is out of scope. Include anti-goals.

    ## Context and Orientation

    Describe the current state of the domain or workspace as if the reader knows nothing.
    Name the key resources, systems, roles, and locations. Define non-obvious terms at the
    point of use — do not collect definitions here as a glossary.

    ## Reference Materials

    List the source materials this plan depends on and explain why each one matters. Name any
    material that must be provided by a stakeholder before execution can begin.

    - <n>: <why it matters and how it will be used>
    - <n>: <why it matters and how it will be used> [MISSING — recorded in Open Questions]

    ## Progress

    - [x] (2026-01-01 09:00Z) Example completed step.
    - [ ] Example incomplete step.

    ## Surprises and Discoveries

    - Observation: …
      Evidence: …

    ## Decision Log

    - Decision: …
      Rationale: …
      Alternatives considered: …
      Date/Author: …

    ## Open Questions

    - Question: …
      Resolved by: …
      Blocks: …

    ## Outcomes and Retrospective

    Compare result against Intention. State what remains open and what was learned.

    ## Plan of Work

    A short narrative of the full sequence: what happens in what order and why that
    order makes sense. This is not a task list — it is an explanation of the strategy.

    ## Milestones

    ### Milestone 1 — <title>

    A short paragraph describing the state change: what will exist at the end that did
    not exist before, what work produces it, and what the executor must demonstrate to
    consider it closed.

    Acceptance criteria:
    - <Observable outcome, not internal state.>

    Concrete Steps:

    1. <What to do and where. Expected outcome: what success looks like. If the step
    depends on a condition or can fail in a known way, describe it here.>

    2. <Next step. Expected outcome: what to observe to confirm it worked.>

    ### Milestone 2 — <title>

    …

    Concrete Steps:

    1. …

    ## Validation and Acceptance

    Describe how to verify that the work as a whole is complete. End-to-end check that
    confirms all milestones together delivered the intended outcome — not a repetition
    of per-milestone acceptance criteria.

    ## Reversibility and Recovery

    State whether steps can be safely repeated. Identify risky or irreversible steps and provide
    recovery paths.

    ## Deliverables and Dependencies

    Deliverables: name every artifact this plan must produce with enough specificity
    that a reviewer can confirm it exists and is correct without asking anyone.

    Dependencies: name every external requirement the deliverables must satisfy or
    integrate with — interfaces, services, or contracts. Do not list reference materials
    here; those belong in Reference Materials above.

After each milestone, create a separate Milestone Report file — see the Milestone Reports section of these instructions for the required structure.
