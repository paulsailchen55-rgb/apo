# Resident Feedback & Evidence Bridge — Conversation Record

**Archive status:** Civic Flow Chart component / conversation-derived design specification  
**Date:** 2026-09-18

## Core idea

The Civic Flow Chart should map not only the path a resident takes through a civic process, but also the path that the resident's observation takes back into the system.

A person may report a problem while actually using a civic system: confusion, delay, noise, a broken handoff, repeated work, an unexpected cost, a useful feature, or another condition worth recording.

The resident should not have to become an activist, survey respondent, lawyer, journalist, or technically sophisticated user merely to leave an observation.

## Two observation moments

### In-the-moment experience

The person reports near the event, preserving the node, approximate time, circumstances, and what happened. Optional emotion or condition can be preserved as context.

The immediate account is evidence of what the person reported at that time. It is not automatically an independently verified external fact.

### Later reflection

The person may later add a reflection after having time to process the experience. This may add remembered facts, revise wording, distinguish reaction from considered assessment, or state what the person now thinks should change or remain.

Later reflection is not automatically more accurate. Memory, social influence, incentives, and subsequent information can affect it.

The original observation should not silently disappear because a later reflection exists.

> **Preserve the observation close to the event; preserve the reflection after time has passed; preserve the relationship between them.**

## Minimal event

**NODE · TIME · OBSERVATION · CONDITION · ROUTE · RECEIPT · STATUS**

The system should permit a very small report. A person may only need to communicate:

> **THIS HAPPENED HERE.**

Routing and recordkeeping should not require the resident to understand the full government architecture.

## Evidence loop

**EXPERIENCE → REPORT → RECEIPT → ROUTING → REVIEW → DECISION/RESPONSE → RECORD → AGGREGATE/LEARN → MAP/PROCESS REVIEW**

This is a feedback architecture, not a guarantee that a report produces a policy or operational change.

## Distinct roles

- Reporter — supplies the observation.
- Receiver — first receives the report.
- Router — identifies the relevant destination.
- Responsible operator — operates/administers the system.
- Reviewer — evaluates evidence or patterns.
- Authorized decision-maker — has authority to make the relevant decision.

Receipt does not equal authority. Receipt does not equal agreement. Receipt does not guarantee change.

## Status and correction

A useful receipt can identify the receiving system, process/node, safe reference identifier, current status, next step/review path, and correction or additional-information path.

Possible statuses may include received, routed, under review, verified, unverified, insufficient information, referred, merged with an existing issue, no action, action taken, or decision pending, where an actual implementation supports those states.

A low-friction correction signal is:

> **THIS LOOKS WRONG.**

The system should preserve the previous version and route the correction without requiring the resident to understand the whole architecture.

## Surveys and continuous feedback

Standing feedback and formal surveys answer different evidence needs. Standing feedback can preserve observations near actual system use. A survey can deliberately sample a defined population and standardize questions later.

Neither method should automatically be treated as a complete representation of public experience. They can be compared and used together.

## Incentives and distortion

Reports can be influenced by fear, embarrassment, time pressure, social pressure, campaign or organizational goals, memory, expectations, question wording, and who collects the information.

The goal is not to manufacture perfectly neutral testimony. It is to preserve provenance and context so later users can interpret the record.

## Emotion and verification

Immediate emotion should not be erased merely because it is emotional. At the same time, emotional expression does not automatically establish an external fact.

Preserve:

**WHAT THE PERSON EXPERIENCED / REPORTED**

separately from:

**WHAT CAN BE INDEPENDENTLY VERIFIED**

## Privacy and aggregation

A conceptual privacy ladder is:

**PRIVATE CASE DATA → RESTRICTED CASE RECORD → DE-IDENTIFIED AGGREGATE → PUBLIC PATTERN / EVIDENCE**

Actual implementation must follow applicable privacy, security, records-management, accessibility, and public-records requirements. The archive does not promise anonymity or universal public disclosure.

## Ledger integration

The bridge can feed a ledger containing node, time, observation type, immediate observation, later reflection, provenance category, verification status, routing destination, receipt status, response status, aggregation status, relevant clock, and observed or proposed consequence.

The ledger should distinguish individual observation from aggregated pattern and independently verified fact.

## Continuous inflow and capacity

Continuous reports could become their own burden. An implementation must test volume, triage, routing accuracy, staff workload, duplication, spam, and the possibility that the feedback channel becomes new friction.

The map should expose where the feedback process itself has a bottleneck.

## Participation bias

A standing feedback channel does not automatically represent everyone. People with more time, confidence, technology, language access, or institutional familiarity may report more often.

Aggregation should therefore show participation limits where material rather than implying a census of public experience.

## Boundaries

This component is part of Civic Flow, not a replacement for formal complaints, petitions, public comment, surveys, emergency reporting, legal processes, or other established channels.

It does not decide policy. It routes observations toward the relevant people and institutions and records what happens afterward where the implementation can lawfully do so.

## Core principles

1. Preserve immediate experience.
2. Preserve later reflection.
3. Do not force either to overwrite the other.
4. Separate observation from verification and interpretation.
5. Map routing and authority separately.
6. Provide receipt without implying agreement.
7. Preserve privacy where required.
8. Keep reporting lightweight.
9. Show uncertainty and participation limits.
10. Test whether the feedback mechanism itself becomes friction.

## Open questions

- What is the minimum report that remains useful?
- What routing data are required to identify the responsible organization without exposing unnecessary personal information?
- What legal records obligations attach to reports and status histories?
- How should anonymous, pseudonymous, and identified reports differ?
- How should repeated or coordinated reports be aggregated without erasing genuine experience?
- How should staff workload and triage be measured?
- How should a resident obtain a copy or correction of their own record?
- What evidence threshold is appropriate for changing a map versus merely flagging an issue for review?
