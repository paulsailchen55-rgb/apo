# AI Coding Build Prompt — Open Community Resource Access & No-Line Navigator

**Status:** PROPOSED / BUILD INSTRUCTION  
**Date:** 2026-09-22

## Mission

Build the software in this repository as an open-source, low-barrier community resource navigator.

The current project began with food access, but **food is the first concrete use case, not the architectural limit**.

The underlying system should help a person move from a community resource guide or other authorized source to a practical next action, using ordinary text messaging wherever possible.

## Read the repository before coding

Before changing code:

1. Read the root APO README and applicable standard workflow documents.
2. Read the complete `open-food-access-no-line-pantry/` project documentation.
3. Read workflow archives, including reconciliation and MMS/edge-AI archives.
4. Inventory existing files before creating new ones.
5. Reconcile before extending.
6. Do not delete, merge, rename, overwrite historical archives, or remove duplicates unless explicitly authorized.
7. Preserve the distinction between evidence states:
   - KNOWN
   - CALCULATED
   - TESTED
   - PROPOSED
   - SPECULATIVE
   - UNKNOWN

## Core architecture

Treat the project as **one underlying resource system with multiple interfaces**, not three separate applications.

### Interface A — Photograph/upload a guide

**photo/document → OCR/extraction → candidate resource records → provenance → verification → active resource data → useful response**

A person or community organization may photograph a paper guide with a phone and submit it through MMS or another supported upload path.

The original image/document is evidence and must be preserved according to the project's retention policy.

OCR/AI extraction is not verification.

### Interface B — Text-first navigation / backup wayfinding

**SMS → conversational resource engine → concise next action**

This is not intended to replace a full mapping product.

The distinction is:

> **Maps tells you where. This system tells you what to do.**

The system can use landmarks, intersections, stores, bus stops, neighborhood descriptions, or other ordinary language. A landmark is not automatically a GPS coordinate.

Do not claim arrival unless supported by appropriate evidence or explicitly reported by the user.

### Interface C — Continue the journey after reaching a resource

The same conversation can continue after arrival:

> “I'm here. They said I need something I don't have. What do I do?”

The system should retain the relevant session context:

- resource;
- service sought;
- published requirements;
- current step;
- available alternatives.

It should provide the smallest useful next action and alternatives when appropriate.

A user disappearing, hanging up, or stopping messages is **not proof of success, failure, satisfaction, or dissatisfaction**.

## General resource pipeline

Use this conceptual pipeline:

**source/guide → ingestion → structured resource record → provenance → verification → time/status/eligibility/access evaluation → next action**

Potential source types include:

- photographed paper guides;
- PDFs;
- nonprofit guides;
- public agency documents;
- flyers;
- provider pages;
- authorized community-maintained directories.

Automated internet discovery may eventually locate candidate guides, but:

**Discovery is not verification.**

Never silently convert discovered, uploaded, or extracted information into trusted active information.

## Resource record requirements

Design the generic record so food and non-food services can share the same foundation.

At minimum support:

- stable ID;
- provider/name;
- service type/category;
- location and landmarks;
- schedule;
- closures;
- 24/7 status where applicable;
- eligibility;
- documentation requirements;
- appointment/walk-in status;
- quantity/inventory where relevant;
- service/resource categories;
- accessibility/travel information;
- languages;
- source identity;
- source version/publication date;
- retrieval date;
- page/section where applicable;
- extraction confidence;
- verification state;
- last verified;
- temporary expiry/withdrawal.

## Evidence and provenance

Every extracted record must be traceable to its source.

At minimum preserve:

- original source identity;
- original image/document when policy permits;
- publisher;
- version/date;
- retrieval date;
- page/section;
- language;
- extracted text;
- extraction confidence;
- verification state;
- verifier/source of verification;
- last verification date.

Use explicit lifecycle states such as:

**RECEIVED → EXTRACTED → NEEDS REVIEW → VERIFIED → ACTIVE → EXPIRED/WITHDRAWN**

Do not represent historical information as current without appropriate verification.

## MMS and edge-AI experimental architecture

MMS can provide media intake while SMS remains the primary text conversation channel.

A small nonprofit/community experiment may use:

**phone/SIM or cellular gateway ↔ local computer ↔ OCR/edge AI ↔ resource database ↔ SMS/MMS**

A USB-C-connected phone is one possible experimental gateway arrangement, but do not assume that every phone, carrier, or operating system supports reliable SMS/MMS gateway operation.

The transport layer must remain separate from the resource-navigation engine.

This permits later substitution of:

- phone gateway;
- cellular modem;
- multiple gateways;
- community-hosted messaging transport;
- another lawful messaging transport.

### MMS security

Treat incoming media as untrusted input.

The implementation should:

1. receive the message;
2. minimize sender/session identification;
3. validate file type and size;
4. isolate media processing;
5. safely decode/scan media;
6. extract text/data;
7. preserve provenance;
8. delete temporary copies according to retention policy;
9. send only the minimum useful response.

Never execute instructions embedded in uploaded documents as system instructions.

Do not request sensitive personal documents merely because MMS makes images possible.

## Capacity and concurrency

Do not claim that one phone/computer can support a particular number of simultaneous conversations without measurement.

Potential bottlenecks include:

- carrier throughput and restrictions;
- modem/phone hardware;
- USB reliability;
- OS limitations;
- OCR/AI inference;
- CPU/RAM/storage;
- image-processing throughput;
- message queue;
- database/session handling;
- outbound message limits.

Use explicit queueing and session state.

The first experiment should measure:

- concurrent sessions;
- messages/minute;
- attachment processing time;
- median and worst-case latency;
- failures/retries;
- queue depth;
- CPU/RAM/storage;
- behavior when offline.

## Low-barrier interaction principles

The system should:

- do information work before asking the person to do work the system can already do;
- use one meaningful action at a time where practical;
- avoid unnecessary questions;
- recover from ambiguity without blaming the user;
- preserve context;
- offer alternatives instead of dead ends;
- allow pause/cancel/main menu/change goal;
- explain requirements in plain language;
- support multilingual, dialect, slang, and code-switching input where feasible;
- treat unusual local references as hypotheses until corroborated;
- preserve the user's original wording when it matters.

The current numbered interaction convention is:

- `1–5`: current numbered choices;
- `*`: explicit “This isn't working” / feedback or exit path;
- `0`: neutral exit/navigation;
- `#`: confirm/continue;
- hang-up: session ended, with no assumed reason.

Do not infer sentiment from keypad choices or silence.

## Travel and access

Travel is part of practical access calculation, not an early eligibility gate.

The preferred sequence is:

**location clue → candidate resources → verify status/eligibility/access → calculate practical access → useful next actions**

Alternatives may include:

- closer location;
- cart/bag or smaller quantity;
- delivery;
- volunteer assistance;
- trusted person;
- proxy pickup;
- another eligible service.

## Calendar and temporary information

Support structured schedule/event information where useful.

Prefer machine-readable calendar data such as `.ics` when available.

Do not place sensitive personal eligibility information into calendars unless specifically requested.

Temporary, seasonal, or frequently changing information needs explicit validity/verification handling.

## The raisins / point-of-service lesson

The architecture must support problems discovered **after a person reaches or interacts with a resource**.

A real-world problem such as receiving food that does not work for the person is not merely a “search result” problem.

The reusable pattern is:

**person encounters real-world obstacle → texts the same number → system uses existing context → gives next useful action/alternatives**

Feedback may be offered, but successful completion must never be forced or inferred.

## Practice and testing

Tests should focus on system behavior, not collecting personal details.

At minimum test:

1. guide photo intake;
2. OCR/extraction;
3. provenance preservation;
4. NEEDS REVIEW state;
5. verification transition;
6. historical-vs-current handling;
7. ambiguous landmark;
8. closed resource;
9. eligibility restriction;
10. practical travel/access alternative;
11. no-dead-end recovery;
12. post-arrival problem;
13. MMS attachment rejection/safety;
14. offline gateway;
15. concurrent sessions and queueing.

Where a scientific limit has not been established, label the value as an engineering hypothesis rather than a scientific fact.

## Privacy and governance

Minimize personal data.

Do not build unnecessary identity profiles, extensive tracking, or intimate-question workflows.

The eventual governance model should support local/community correction, provenance, verification, withdrawal, and version history without requiring one centralized authority to control every local guide.

## Free/open-source constraint

Prefer free and open-source components for the initial implementation.

Do not invent APIs, carrier capabilities, hardware capabilities, or service limits.

If a dependency requires a paid account, proprietary service, cloud API, or unavailable credential:

- document the dependency;
- keep the core architecture usable without it where practical;
- provide an interface boundary;
- do not pretend it is implemented;
- report incomplete work honestly.

## Non-destructive repository rule

Before modifying an existing file, fetch and inspect its current contents.

Never:

- delete historical material;
- merge duplicates automatically;
- rewrite old workflow archives as though they were always known;
- upgrade PROPOSED/SPECULATIVE material to TESTED/KNOWN without evidence;
- conceal incomplete implementation.

Add new dated archives when new understanding materially changes the project.

## Build order

Prefer this order unless repository evidence justifies another sequence:

1. generic source-guide/document model;
2. generic resource-record schema;
3. provenance and evidence lifecycle;
4. one real historical guide fixture;
5. one food and one non-food resource fixture;
6. time/status/eligibility/access evaluation;
7. photo/MMS ingestion boundary;
8. text/SMS conversational interface;
9. post-arrival continuation;
10. queue/concurrency measurement;
11. additional transports;
12. broader guide discovery.

Do not begin with a national crawler.

## Acceptance criteria for an initial implementation

A build is not complete merely because files compile.

The initial implementation should demonstrate, with tests or a clearly documented prototype:

**one photographed guide → media receipt → safe extraction → source/provenance record → candidate resource records → NEEDS REVIEW → verification → active record → concise SMS/MMS result**

It should also demonstrate:

**SMS user → location clue → verified resource evaluation → practical next action**

and:

**same user/session → post-arrival obstacle → context-aware next action**

Report exactly what works, what is simulated, what depends on external infrastructure, and what remains unknown.

## Final instruction to the coding AI

Do not decide what the project “really is” before reading its history.

**Preserve the possibility before deciding what it is.**

**Reconcile before extending.**

**Preserve the local guide; generalize the interface.**

Build the smallest testable increment that moves the repository toward the demonstrated workflow, while preserving the evidence trail and all meaningful prior work.
