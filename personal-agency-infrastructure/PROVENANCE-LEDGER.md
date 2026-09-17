# Provenance Ledger

## Purpose

The provenance ledger preserves the path from an original human statement to any later representation, including AI transformations, human corrections, collective aggregation, and institutional submission.

The objective is not to make AI output authoritative. The objective is to make transformation visible and contestable.

## Transformation chain

A conceptual chain is:

```text
H0  Human original
 |
 v
AI1 AI interpretation
 |
 v
H1  Human correction
 |
 v
AI2 AI reformulation
 |
 v
H2  Human approval or edit
 |
 v
COLLECTIVE1  Group aggregation or collective review
 |
 v
AUTHORITY1  Submission to an institution
```

Each step should preserve a reference to the preceding artifact rather than silently replacing it.

## Example

Original human statement:

> They keep making me do this stupid form.

AI interpretation:

> Tenant reports repeated difficulty completing a required form.

Human correction:

> I want it to say I cannot complete it without assistance.

Final representation:

> Tenant reports that they cannot complete the required form without assistance.

The final sentence is useful to an institution, but the system must still retain the original statement, the AI interpretation, and the person's correction.

## Attribution labels

Possible provenance labels include:

- Human-authored
- AI-generated
- AI-transformed
- Human-edited
- Human-approved
- Collectively approved
- Externally verified

These labels describe how a representation was produced. They do not, by themselves, determine whether the underlying claim is true.

## Evidence and authority

Provenance should be connected to relevant supporting material where available:

- original communication
- documents
- recordings
- correspondence
- governing law or regulation
- contract language
- policy
- external evidence
- human corrections
- institutional responses

A provenance record should not imply verification merely because a source exists. Source existence and factual truth are separate questions.

## Collective aggregation

A collective document may summarize recurring experiences across people, but aggregation must not destroy individual provenance.

A useful design rule is:

> Aggregate patterns without erasing the people and records from which the pattern was derived.

Privacy controls must determine what individual information is exposed in a collective output.
