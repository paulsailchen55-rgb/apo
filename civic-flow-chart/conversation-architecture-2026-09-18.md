# Civic Flow Chart — Conversation Architecture Record

**Archive status:** Conversation-derived reference package  
**Date:** 2026-09-18  
**Role in apo:** Reference / chat-loader material; not the active project repository.

## Provenance and boundary

This record consolidates the Civic Flow Chart architecture developed in the available conversation context. It is not a government standard, legal description of any jurisdiction, or proof that the proposed feedback infrastructure currently exists.

The active implementation/workbench is maintained separately. This archive exists so future conversations can recover the conceptual model, its distinctions, and its unresolved questions.

## Purpose

The Civic Flow Chart is an explanatory and navigation layer for complicated civic processes. It maps existing systems without replacing government authority. Official laws, regulations, records, fees, deadlines, decisions, and operational instructions remain authoritative at their sources.

The framework is intended to work without AI, social media, user accounts, or specialized technology. It should be usable in print, through libraries, in basic HTML, and eventually in interactive software.

## Basic routing

**WHERE ARE YOU? → WHAT ARE YOU TRYING TO DO? → WHO HAS AUTHORITY? → WHO IS RESPONSIBLE FOR THE NEXT ACTION?**

## Child Test

A usable explanation should help a person answer:

1. What is happening?
2. What am I trying to do?
3. Where am I in the process?
4. Who decides?
5. Who is responsible for the next step?
6. What do I need to do?
7. Why is this required?
8. What does it cost?
9. How long should it take?
10. What if I cannot do it?
11. What happens next?
12. Can I go back, pause, appeal, or exit?
13. Where can I verify this?

The Child Test tests understandability; it does not claim the underlying process is simple.

## Node model

A node may contain:

**SPACE · TIME/CLOCK · PRIORITY · AUDIENCE · AUTHORITY · RESPONSIBILITY · INPUT · ACTION · STATUS · MONEY · NEXT · BACKTRACK · EXIT**

Unknown information should remain explicitly **UNKNOWN / NOT YET MAPPED** rather than being filled by assumption.

## Clock model

Keep separate:

- legal clock;
- administrative target;
- observed duration;
- resident elapsed time;
- financial clock.

A map should identify source, start point, type, expected duration/deadline, and known consequences of delay.

## Friction

Ask:

> **What is this friction doing?**

before:

> **What do I need to do?**

Friction may serve safety, environmental, participation, rights, accessibility, or accountability functions while also imposing burdens. The map should make both purpose and burden inspectable.

## Reversibility

Distinguish navigation backtracking, administrative correction, appeal/review, legal reversibility, physical reversibility, and irreversible consequences.

## Current versus proposed

**CURRENT PROCESS** and **PROPOSED ALTERNATIVE** must remain visibly separate. A proposal must never appear to be an existing rule.

## Three views

The same graph can be presented as:

- **Resident Map:** What am I trying to do?
- **Government Map:** Who is responsible?
- **Flow Map:** How does it move?

## Twelve master doors

1. Home, Land & Building
2. Money, Taxes & Economic Security
3. Health & Human Services
4. Roads, Transportation & Public Space
5. Water, Waste & Environment
6. Safety & Emergencies
7. Animals & Agriculture
8. Records, Information & Identity
9. Civic Participation
10. Justice, Rights & Accountability
11. Work, Business & Procurement
12. Government IT & Digital Access

These are navigation categories, not a claim that government has only 12 components.

## Emergency mode

Emergency presentation may begin:

**WHAT IS HAPPENING? → WHERE? → IS ANYONE IN IMMEDIATE DANGER? → WHAT NEEDS TO HAPPEN NOW?**

Possible operational sequence:

**LIFE/SAFETY → IMMEDIATE HAZARD → CRITICAL INFRASTRUCTURE → ESSENTIAL SERVICES → RECOVERY → NORMAL CIVIC BUSINESS**

This is an operational sequence, not a moral ranking.

## Evidence model

Maintain distinctions among:

**FACT → MODEL → ESTIMATE → OPINION**

Source records should capture source type, source owner, authority type, date, purpose, scope, current status, evidence/basis, and review status.

A scientific paper can provide evidence without being government authority. A government webpage may explain a process without being the underlying legal source. Historical evidence documents the past rather than automatically establishing current policy.

## Ledger / Lab / Archive

**Ledger:** friction, clocks, evidence, failed handoffs, stakeholder costs, verification questions, proposed changes, and simple correction signals.

**Lab:** alternatives and simulations.

**Archive:** prior maps, source versions, plans, decisions, assumptions, and superseded pathways.

The ledger must not become a new bureaucracy.

## Memory / Continuity / Renewal

Civic Memory preserves what existed and what was learned. Civic Continuity carries useful knowledge through change. Civic Renewal reviews what continues, changes, is replaced, retires, or remains as history.

Lifecycle:

**ALPHA → LIFE → OMEGA → REVIEW → RENEWAL → ALPHA′**

Preferred public wording: **Lifecycle Review / Renewal Cycle**.

> The purpose survives the version. The version does not become the purpose.

## Completion and contribution

Distinguish:

- Official Record
- Process Record
- Experience Record
- Outcome Record
- Archive

**ENDPOINT ≠ COMPLETION ≠ CLOSURE**

Contribution should not become a bureaucratic measure of human worth. Contribution is not ownership; recognition is not authority.

## System Gravity

A working metaphor for resistance between civic states/nodes: time, money, distance, knowledge, physical access, technology, uncertainty, authority, and risk.

This is not a claim about a physical scientific force.

## Maintenance and staleness

Time-sensitive nodes should track source owner, source location, last verified, effective date/version, review trigger, and reviewer/responsible organization.

Valid states include **UNKNOWN / NOT YET MAPPED** and, where appropriate, **DISPUTED**.

> The map does not have to settle every disagreement. It has to make the disagreement inspectable.

## Self-audit

Ask whether Civic Flow itself is becoming:

- authority instead of explanation;
- bureaucracy instead of access;
- a source of false certainty;
- a gatekeeper;
- a system that privileges sophisticated users;
- a process whose correction channel creates more friction;
- a system resistant to its own replacement.

A core question is:

> **What happens if the Civic Flow Chart itself becomes friction?**

## Success criteria

A resident should be able to identify the start, next responsible actor, authority versus explanation, legal deadline versus estimate, known costs/consequences, review/appeal/correction/backtrack/exit, source, and uncertainty.

Staff and institutions should be able to see handoffs, unclear responsibility, repeated work/friction, corrections, versions, and resident experience.

## Development sequence

**RESEARCH → MAP → CHILD TEST → SUBSTANTIVE REVIEW → STRUCTURAL REVIEW → RENDERING REVIEW → RECIPIENT REVIEW → RELEASE → OBSERVE → REVISE → ARCHIVE**

Working rule:

**Fast production. Slow release.**

## Relationship to neighboring work

Government Authority / Responsibility Map asks who can decide, recommend, review, enforce, fund, regulate, or route. Civic Flow asks what the resident encounters step by step. They should inform each other but remain distinct.

Personal Agency Infrastructure supplies broader provenance, permissions, routing, and AI-transformation principles. It is related infrastructure, not the Civic Flow project itself.

The 1214 Soquel / Seabright work is a site-specific test case. It should not define the general framework.

## Technical future

Possible later technical layers include machine-readable node/edge schema, JSON/open data, HTML/print rendering, interactive maps, source verification, lightweight ledger functions, archive/version comparison, emergency views, and APIs.

Technology should implement the model rather than silently redefine it.

## Open questions

- Which civic processes are most useful as initial tests?
- What is the smallest viable node schema?
- How should source verification and staleness be displayed in print and basic HTML?
- How should jurisdictional overlap be represented without implying false coherence?
- What is the minimum viable resident feedback channel?
- What privacy, security, records, and accessibility rules apply to an actual implementation?
- How can continuous observations be useful without overwhelming responsible staff?
- How should participation bias and aggregation limits be displayed?
