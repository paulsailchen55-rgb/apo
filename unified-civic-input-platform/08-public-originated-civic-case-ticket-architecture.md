# Public-Originated Civic Case / Ticket Architecture

**Status:** PROPOSED  
**Origin:** September 15, 2026 Santa Cruz County Board of Supervisors public-comment observation and subsequent discussion  
**Evidence state:** OBSERVED / PROPOSED / UNKNOWN distinctions are used below. This document does not claim that Santa Cruz County currently lacks any particular system until that is researched.

## Core idea

Residents need a legitimate bottom-up way to create a civic **case/ticket** without first knowing which government department, official, jurisdiction, or bureaucratic category is responsible.

The resident reports the problem. The public system creates the case. Government determines routing. The case records what happens. The responsible level acts. The case escalates only when necessary. The history remains.

> **Start where the problem is experienced. Resolve it at the lowest appropriate level. Escalate only when necessary. Preserve the record all the way up.**

## Why the ticket matters

In corporate and government software workflows, a ticket/case/work order can carry a problem through an organization. It can acquire an identifier, timestamps, assignments, status changes, approvals, inspections, financial information, correspondence, actions, and outcomes.

The civic gap this project is exploring is the **public-originated front door** to that machinery.

The resident should not have to perform the routing manually.

### Proposed pathway

```
RESIDENT
   ↓
PUBLIC CIVIC INTAKE
   ↓
CASE / TICKET CREATED
   ↓
TRIAGE + CLASSIFICATION
   ↓
ROUTING
   ↓
RESPONSIBLE CITY / COUNTY / OTHER PUBLIC OFFICE
   ↓
INVESTIGATION / ACTION
   ↓
RESULT
   ↓
ESCALATION IF NECESSARY
```

## Bottom-up rather than top-down

A conventional complaint can effectively become:

```
Resident → elected official → staff → department → action
```

The proposed architecture is:

```
Resident
   ↓
Civic intake
   ↓
Local case
   ↓
Appropriate department
   ↓
Department management
   ↓
Higher administrative authority
   ↓
Elected decision-making body when a policy-level decision is actually required
```

The Board of Supervisors should be reachable, but it should not necessarily be the first place every problem must go.

## Only as high as necessary

Escalation should be based on published rules and documented case history.

A routine service issue might stop at the responsible department.

A cross-department problem might require management coordination.

A persistent unresolved systemic problem might require higher administrative or policy-level attention.

The purpose is not to create another mandatory bureaucratic layer. The purpose is to make the existing administrative machinery easier for residents to reach.

## Physical and digital access

A library could provide a public access point, but librarians should not be made responsible for investigating, triaging, or legally classifying cases.

Possible entry points:

- web;
- library/public computer;
- public kiosk;
- telephone;
- paper-assisted intake;
- accessibility services;
- other approved public-service channels.

All channels should feed the same underlying civic case architecture.

## AI's role

AI could assist with:

- classification;
- routing suggestions;
- deduplication of related reports;
- summarization;
- translation;
- accessibility;
- trend detection;
- case-history synthesis;
- identification of cases that may require escalation review.

AI should **not** silently become the final authority on emergency status, legal status, enforcement, or public policy.

A machine classification should remain distinguishable from a human/government determination.

Human review, correction, auditability, and published rules are important.

## Evidence states

The system should distinguish:

**REPORT** — a resident says they experienced or observed something.

**SUPPORTING EVIDENCE** — documents, photographs, recordings, measurements, correspondence, or other supporting material.

**RELATED REPORTS** — other reports concerning the same underlying condition.

**VERIFIED** — an appropriate public authority confirms relevant facts.

**ACTION** — an authority records an action.

**RESOLVED** — the responsible authority records resolution under its applicable process.

This permits early reporting without turning an unverified allegation into an established government finding.

It also prevents incomplete initial evidence from becoming a reason that residents cannot report a problem.

## Institutional memory

A case should preserve its history through changes in staff, departments, administrations, and elected officials.

Potential case history:

- original report date;
- location;
- related reports;
- responsible departments;
- assignments;
- previous actions;
- correspondence;
- inspections;
- decisions;
- escalations;
- current status;
- final disposition.

A long-running problem should not repeatedly return to zero simply because personnel or elected leadership changes.

## Privacy architecture

Not every part of a civic case should be public.

### Public information

Potentially public:

- general location;
- issue category;
- report date;
- aggregate related-report counts;
- responsible agency;
- general status;
- resolution status.

### Restricted information

Authorized personnel may need:

- resident contact information;
- detailed correspondence;
- supporting documents;
- sensitive photographs;
- specific personal circumstances.

### Legally protected information

Information subject to specialized legal protections should remain in appropriate protected systems and should not automatically become part of a public community board.

A civic complaint should not automatically become a law-enforcement record merely because it concerns a difficult subject.

## AI/data access boundaries

AI access should follow information classification.

Public aggregate information may be processed for summarization or trend analysis.

Restricted information should require authorized access and appropriate controls.

Legally protected information should have additional controls.

The system should maintain auditable access records.

## Open-source and government control

This project also raises a public-technology procurement question.

Essential civic infrastructure should, where feasible, avoid permanent dependence on a proprietary subscription vendor.

Preferred properties to investigate:

- open source;
- self-hostable;
- auditable;
- standards-based;
- exportable;
- replaceable;
- maintainable by government or another qualified provider;
- no permanent vendor lock-in;
- government control of civic records.

This does **not** establish that every government system must be open source. It proposes investigating open-source and standards-based systems as a public procurement and continuity strategy.

The principle is:

> If public money creates essential civic infrastructure, the public institution should be able to preserve, inspect, export, maintain, and migrate its records and system.

## Public dashboard

A public dashboard could expose aggregate civic information without exposing personal information.

Possible measures:

- open cases;
- case age;
- aggregate related reports;
- responsible department;
- cases awaiting response;
- escalated cases;
- resolved cases;
- recurring issue categories;
- geographic aggregation.

The goal is institutional visibility, not public shaming of individual workers.

## Questions requiring research

1. What City of Santa Cruz, County of Santa Cruz, or regional systems already accept resident service requests?
2. Which systems already create tickets/cases?
3. Can cases move between departments without forcing the resident to restart?
4. Can related reports be associated?
5. Can cases remain active across administrative changes?
6. What happens when jurisdiction is unclear?
7. What happens when several agencies share responsibility?
8. What are the published triage rules?
9. Who can change triage rules?
10. Can residents see their case status?
11. What aggregate information can be public?
12. What information is legally restricted?
13. How are public-record obligations handled?
14. What existing open-source case-management platforms could work?
15. What procurement rules affect open-source adoption?
16. Can complete records be exported in open formats?
17. Can government migrate away from a vendor without losing historical records?
18. What role should libraries actually play?
19. What decisions must remain human decisions?
20. How should AI routing errors be corrected?
21. How should duplicate reports be handled?
22. How should independent reports be distinguished from copied submissions?
23. What criteria should trigger administrative escalation?
24. What criteria should trigger policy-level escalation?
25. How should emergencies bypass ordinary civic intake?

## Hard to discuss

### Who decides what is urgent?

Triage requires rules. Those rules should not be hidden inside an AI model.

### Who controls the database?

Government control can improve institutional accountability, but government databases can also contain sensitive information. Control must be paired with access controls, auditing, retention rules, and legal safeguards.

### Can the system become surveillance?

Yes, if it collects unnecessary identity or location information. Reporting a neighborhood problem should not automatically require continuous GPS tracking.

### Can AI manufacture consensus?

Yes. Ten copied submissions should not automatically equal ten independent observations. The system should preserve provenance and distinguish duplicate submissions from independent reports.

### Can the system become another bureaucracy?

Yes. The design must be judged partly by whether it actually reduces the resident's burden.

### What if government does not act?

The system cannot guarantee an outcome. It can guarantee, if properly designed, that a report has a durable record, an identified pathway, a documented response, and a legitimate escalation mechanism.

## Design principle

> **The resident reports the problem.  
> The government determines where it belongs.  
> The case records what happens.  
> The responsible level acts.  
> The case escalates when necessary.  
> The history remains.**

## APO evidence tags

**KNOWN:** The project idea is based on the user's observation of public-comment discussion on September 15, 2026 and the user's prior experience with ticket/case-based software workflows.

**PROPOSED:** The bottom-up public-originated case architecture described here.

**PROPOSED:** AI-assisted classification, routing, summarization, deduplication, accessibility, and trend analysis with human oversight.

**PROPOSED:** Government-controlled, open-source/standards-based technology as a procurement and continuity preference.

**UNKNOWN:** The exact capabilities, limitations, legal requirements, procurement constraints, and existing systems of Santa Cruz County and related public agencies.

**RESEARCH NEEDED:** Determine what already exists before proposing new software.

## Next research step

Inventory existing Santa Cruz City/County public service-request, complaint, 311-style, code-enforcement, public-works, and Board-of-Supervisors communication systems before designing a replacement.

---

# Workflow Archive

This file originated from a September 24, 2026 conversation while listening to the September 15, 2026 Board of Supervisors public comments.

The conversation developed through these observations:

1. Residents were using limited public-comment time to communicate complicated issues.
2. At least one speaker discussed triage.
3. The user heard discussion of a problem persisting for more than ten years.
4. The user observed that residents may lack a clear place to communicate long-running problems before they reach the Board.
5. The initial concept was a physical/digital community board associated with a library.
6. The concept then shifted toward a government-controlled civic intake system because librarians should not be burdened with legal, administrative, privacy, and routing responsibilities.
7. The user's prior experience with corporate/government software led to the recognition that the **ticket/case** is the useful administrative object.
8. The user emphasized that a resident-originated ticket can then travel through departments, approvals, inspections, finance, management, and decision-making structures.
9. The concept therefore became a **public-originated civic case/ticket architecture**, rather than simply a public comment board.
10. The user also raised concern about perpetual software subscriptions and proposed that essential public infrastructure should investigate open-source, government-controlled alternatives.
11. Privacy and legal accountability led to the separation of public, restricted, and legally protected information.
12. The project was posted to preserve the idea before further research determines which portions already exist in current government systems.

No claim in this archive should be treated as proof that an existing Santa Cruz government system does or does not already provide any particular capability.
