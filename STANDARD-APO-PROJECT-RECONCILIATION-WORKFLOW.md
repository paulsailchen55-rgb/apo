# Standard APO Workflow: Project Reconciliation and Recovery

## Purpose

This is a reusable APO process for taking an existing project, conversation-derived body of work, or partially developed idea and reconciling it before adding more implementation.

It answers: What do we already have? What was recovered? What is missing? What overlaps but should remain distinct? What is unresolved? What should be built next?

The goal is to prevent both loss of ideas and premature consolidation.

## When to use this workflow

Use it when a project has accumulated many archives, earlier conversations appear to contain missing material, implementation has drifted from the original problem, new ideas may already exist elsewhere, duplicate-looking files may actually represent different stages, or the next implementation step is unclear.

Do not use reconciliation as a reason to delete or merge material automatically.

## Core principle

> **Reconcile before extending.**

Before adding another feature, determine what the project already knows, what it does not know, and what the next meaningful implementation boundary is.

## Standard reconciliation sequence

### 1. Establish scope

Identify the repository, project folder(s), relevant archive material, current implementation status, and requested change. Do not assume everything with a similar name is the same project.

### 2. Inventory existing material

Inspect relevant README, architecture, design, research, prototype, test, workflow archive, recovery archive, open-question, roadmap, source/provenance, supporting-concept, and historical/superseded files.

Preserve meaningful duplicates unless their relationship has been explicitly resolved.

### 3. Recover missing context

Use available prior conversation/archive material to identify ideas that are not adequately represented in the current project. Preserve provenance and evidence status. Do not reconstruct unavailable history as if it were known.

### 4. Reconcile into four buckets

**A. ALREADY CAPTURED** — adequately represented; no new file required unless a cross-reference is useful.

**B. RECOVERED / MISSING** — important material exists elsewhere but is not adequately represented; create a focused archive or project file.

**C. OVERLAPPING / DISTINCT** — related items have meaningful differences; preserve both and document the relationship rather than merging them.

**D. UNRESOLVED** — relationship, meaning, evidence, implementation, or priority cannot yet be determined; record it in the appropriate uncertainty or open-question file.

### 5. Identify the implementation boundary

After reconciliation, ask:

> What is the smallest reliable foundation that allows the existing ideas to operate without pretending unresolved information is known?

Prefer a concrete foundation over another conversational demonstration.

Examples include data schema before UI, source/provenance model before automated claims, evaluator before user-facing recommendation, test fixture before broad integration, permission model before document upload, and interface state machine before conversational polish.

### 6. Preserve evidence status

Use the APO evidence vocabulary where appropriate:

- KNOWN
- CALCULATED
- TESTED
- PROPOSED
- SPECULATIVE
- UNKNOWN

Do not silently upgrade a proposal into a fact. When a proposal becomes tested, record that transition.

### 7. Create the reconciliation archive

For a substantial reconciliation, create:

WORKFLOW-ARCHIVE-YYYY-MM-DD-PROJECT-RECONCILIATION.md

Record the purpose, material examined, what was already represented, recovered material, overlapping-but-distinct material, unresolved questions, implementation direction, evidence/uncertainty notes, provenance, and limitations.

This is a historical snapshot. It does not replace earlier workflow archives.

### 8. Update open questions

If reconciliation exposes unresolved implementation or research questions, add or create OPEN-QUESTIONS.md. Do not fill gaps with guesses merely to make the project appear complete.

### 9. Build the next waypoint

Only after reconciliation should the next implementation artifact be selected. It should be concrete, small enough to test, connected to the actual problem, based on known or explicitly marked assumptions, and capable of revealing what needs to be learned next.

### 10. Archive the transition

After meaningful implementation work, create the appropriate workflow archive describing what changed from the previous state.

The archive chain should make it possible to understand:

conversation → recovery → reconciliation → implementation → test → revision

## Non-destructive rules

Unless the user explicitly approves otherwise:

- do not delete existing files;
- do not merge files merely because they overlap;
- do not rename existing work;
- do not overwrite historical workflow archives;
- do not remove duplicates;
- do not turn an archive into a claim of validation;
- do not treat AI-generated interpretation as human-authored fact;
- do not hide uncertainty to simplify the repository.

If two files later prove to be redundant, record that finding first and ask before destructive cleanup.

## Recommended project state model

A project may move through:

EXPLORATION → ARCHIVE → RECOVERY → RECONCILIATION → FOUNDATION → PROTOTYPE → TEST → REVISION → DEPLOYMENT / HANDOFF

Projects do not have to follow every state or move only forward. Returning to recovery or reconciliation is valid when new evidence appears.

## Relationship to the Standard APO Push Workflow

The existing APO push workflow answers:

> What distinct bodies of work emerged, and where should they be archived?

This reconciliation workflow answers:

> Now that a body of work exists, what does it actually contain, what is missing, and what should happen next?

They are complementary.

**Push workflow:** preserve and classify.

**Reconciliation workflow:** compare, recover, distinguish, and establish the next foundation.

## Reusable instruction

> **Reconcile this project before extending it.**
>
> Inspect the existing project files and relevant archived material. Identify what is already adequately captured, what important material has been recovered but is missing, what overlaps but remains meaningfully distinct, and what is unresolved. Preserve existing files and historical archives unless explicitly authorized to modify or remove them. Use KNOWN / CALCULATED / TESTED / PROPOSED / SPECULATIVE / UNKNOWN where useful. Create a dated project-reconciliation workflow archive and update OPEN-QUESTIONS.md when needed. Then identify the smallest reliable implementation foundation that should be built next. Do not add conversational features merely to demonstrate progress when a missing data, provenance, evaluation, permission, or test foundation is the real blocker.

## Guiding principle

> **Preserve the path before optimizing the destination.**
