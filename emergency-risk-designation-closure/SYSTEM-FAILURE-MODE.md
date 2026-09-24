# System Failure Mode and Guardrail Model

## Purpose

This document translates the originating concern into a system-design model that can be tested against an actual policy, program, database, or AI workflow.

It is intentionally neutral about whether the hypothetical failure exists in Santa Cruz County.

## Normal emergency pathway

A bounded emergency system should resemble:

1. **Signal** — someone identifies a possible emergency.
2. **Verification** — an authorized person evaluates the available evidence.
3. **Authorization** — the appropriate authority permits a defined intervention.
4. **Intervention** — only the necessary protective action occurs.
5. **Reassessment** — the condition is reviewed.
6. **Resolution** — the emergency condition is resolved, remains active, or requires a new decision.
7. **Closure** — the intervention ends when its purpose ends.
8. **Disposition** — records receive the treatment required by law and policy.
9. **Separation** — unrelated uses require their own authority.

## Failure pathway

A potentially unstable system could instead behave as:

1. **Signal**
2. **Broad classification**
3. **Automatic escalation**
4. **Continuous observation**
5. **Large-scale record creation**
6. **AI inference**
7. **Discovery of unrelated information**
8. **Reinterpretation of the person**
9. **New risk signal**
10. **Renewed observation**

The central failure is not observation itself.

The central failure is the loss of a reliable boundary between **temporary safety authority** and **continuing institutional access to the person**.

## Extraction loop

A conceptual extraction loop is:

**PERSON → SAFETY CONCERN → DATA COLLECTION → INFORMATION → INFERENCE → INSTITUTIONAL VALUE → JUSTIFICATION FOR MORE DATA**

This loop can be harmful even without an individual actor deliberately intending harm.

A resilient design therefore asks whether the system has a reason to stop that is stronger than its ability to continue.

## Closure loop

A stabilizing design is:

**CONCERN → LIMITED RESPONSE → REASSESSMENT → RESOLUTION → CLOSURE → DISPOSITION**

The two loops should not be equally easy to activate.

Continuation should require renewed justification when the original emergency authority expires.

## Guardrail architecture

### Guardrail 1 — Purpose binding

Every collection event should have an identified purpose.

### Guardrail 2 — Evidence threshold

A classification should require a documented basis appropriate to the seriousness of the intervention.

### Guardrail 3 — Minimum necessary scope

The system should collect and expose no more information than the authorized purpose requires.

### Guardrail 4 — Separate permissions

Observation, classification, inference, retention, disclosure, and action should be independently governed.

### Guardrail 5 — Time boundary

Active emergency status should have a defined clock.

### Guardrail 6 — Reassessment

Continuation should require reassessment rather than being the default state.

### Guardrail 7 — Closure

A closed emergency should produce an explicit closure state.

### Guardrail 8 — Secondary-use boundary

Information obtained for one safety purpose should not automatically become evidence for unrelated purposes.

### Guardrail 9 — Provenance

Human observations, statements, official findings, and AI-generated inferences should remain distinguishable.

### Guardrail 10 — Correction

A person should have a meaningful mechanism for correcting inaccurate information where legally appropriate.

### Guardrail 11 — Derived-data governance

Correcting or deleting a source record should trigger an examination of copied and derived information.

### Guardrail 12 — Auditability

Access, changes, disclosures, renewals, and AI-generated decisions should be auditable.

### Guardrail 13 — Incentive review

System designers should examine whether funding, performance metrics, contracts, staffing, or institutional incentives reward continued classification rather than successful closure.

### Guardrail 14 — Independent oversight

High-consequence extensions of emergency authority should be reviewable by someone other than the person or system that benefits from continuation.

## Red flags for research

The following would be worth investigating if found in an actual policy or technical system:

- no defined expiration;
- indefinite “active” status;
- automatic renewal;
- renewal without new evidence;
- broad proxy definitions;
- unrestricted internal access;
- unrestricted data sharing;
- AI inference treated as fact;
- inability to distinguish source from inference;
- inability to correct false information;
- retention of unnecessary derived data;
- safety records automatically copied into unrelated systems;
- no documented closure event;
- no audit trail;
- success measured primarily by activity or data volume.

A red flag is not proof of misuse. It identifies an architectural feature that deserves closer examination.

## Resilience test

A proposed emergency system should be tested with at least these scenarios:

### Test A — False positive

A person is incorrectly classified as at risk.

**Question:** How quickly and completely can the system correct the error?

### Test B — Resolved emergency

The person receives assistance and the immediate concern ends.

**Question:** What automatically changes in system status?

### Test C — Repeated concern

A genuinely new emergency occurs months later.

**Question:** Can the system respond without treating the old designation as proof of the new one?

### Test D — Unrelated discovery

Information unrelated to the safety purpose is discovered.

**Question:** What prevents automatic repurposing?

### Test E — AI error

An AI system generates an incorrect risk inference.

**Question:** Can the inference be challenged, corrected, traced, and removed or quarantined?

### Test F — Data breach

Sensitive information is exposed.

**Question:** Can the organization determine exactly what was exposed and who accessed it?

### Test G — Vendor change

The technology provider changes or the contract ends.

**Question:** Who controls the records, derived data, models, backups, and deletion process?

### Test H — Jurisdiction change

The person moves between agencies or jurisdictions.

**Question:** Does the risk label follow the person automatically?

## Desired system property

The desired property is not “zero information.”

The desired property is:

> **Information remains connected to a legitimate purpose, and authority expires when that purpose expires unless a new, independently justified authority exists.**

## Core resilience equation

Conceptually:

**EMERGENCY AUTHORITY = PURPOSE + EVIDENCE + SCOPE + TIME + REVIEW**

Not:

**EMERGENCY AUTHORITY = PERSON + LABEL + PERMANENT RECORD**

This is a proposed design abstraction, not a statement of current law.
