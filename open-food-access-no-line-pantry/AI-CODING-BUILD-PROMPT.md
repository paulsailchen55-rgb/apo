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

## Understand the roles of project documents

The repository may contain several kinds of documents. Do not treat them as interchangeable.

- **Current project documents** describe the current architecture, design parameters, roadmap, safety rules, known limitations, and open questions.
- **`AI-CODING-BUILD-PROMPT.md`** is an implementation instruction for a coding AI. It tells the AI what the project is currently asking it to build and how to work safely in the repository.
- **`WORKFLOW-ARCHIVE-*` documents** preserve how an idea or architectural understanding developed. They are historical context and evidence of project reasoning, not automatically new implementation requirements.
- **Practice/test artifacts** demonstrate or exercise behavior and should be distinguished from production implementation.
- **Experimental documents** describe possible technical approaches without asserting that those approaches are validated.

A future coding AI should read all relevant material, but should preserve these distinctions rather than flattening the repository into one undifferentiated specification.

## Adapt the coding workflow to the AI being used

Different coding AIs, agent environments, tool systems, and model families may have different recommended workflows.

Do not assume that one tool's operating procedure applies to every other AI.

Before coding:

1. Identify the capabilities and constraints of the current coding environment.
2. If the AI platform provides an official coding-agent guide, workflow document, PDF, or equivalent instruction, obtain and read it when practical.
3. Adapt the **execution procedure** to that environment.
4. Do **not** change the project's underlying principles merely because the AI's preferred workflow is different.
5. Preserve the repository's evidence states and non-destructive rules.
6. Ask for clarification when the platform's capabilities materially prevent the requested work rather than silently substituting a different project.

The project defines the destination and constraints; the particular AI environment may determine the safest practical work order.

## Core architecture

Treat the project as **one underlying resource system with multiple replaceable interfaces**, not three separate applications.

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

## Modular interface principle

The interfaces must be treated as **replaceable adapters**, not containers for duplicated core logic.

The underlying resource-access system should expose explicit, stable contracts for operations such as:

- submit/ingest source;
- create or retrieve resource records;
- inspect provenance;
- evaluate time/status/eligibility/access;
- establish or continue journey state;
- request a next action;
- report a point-of-service obstacle;
- retrieve alternatives.

An interface may translate human input into these operations and translate results back into its own presentation format.

### Replaceability test

The architecture should permit, in principle:

- removing the photo interface while text navigation continues to work;
- replacing SMS with another transport while the resource engine remains usable;
- adding voice without rewriting the resource model;
- adding a web interface without duplicating eligibility/access logic;
- replacing one OCR implementation without changing the resource records;
- replacing one AI model without making the AI model the source of truth;
- running a kiosk, community computer, or other interface against the same core.

A module is not truly replaceable merely because its code is in a separate folder. **Its removal or substitution should not destroy the underlying resource-access system.**

This is a modular/message-oriented design principle: an interface should need to know what the underlying component can do, not how that component internally does it.

## First-build strategy: smallest modular vertical slice

Do **not** build Interface A, B, and C as three separate applications first.

Do **not** build one giant application that hard-codes all three interfaces together.

Instead, build the **smallest end-to-end vertical slice that exercises all three interfaces while keeping their boundaries replaceable**.

The first demonstration can be intentionally tiny:

**guide image → extracted resource → provenance/review state → text request → useful action → simulated arrival → point-of-service obstacle → context-aware next action**

The purpose of this first build is to prove the architectural relationship:

> **One underlying system, multiple interfaces.**

It is not a requirement to complete every interface, solve production messaging, or deploy publicly.

The first implementation should therefore favor small adapters, explicit interfaces/contracts, test fixtures, and replaceable components over premature infrastructure.

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
7. small replaceable Interface A adapter;
8. small replaceable Interface B adapter;
9. small replaceable Interface C adapter;
10. connect A+B+C through the shared core in one end-to-end demonstration;
11. queue/concurrency measurement;
12. additional transports;
13. broader guide discovery.

The order above is an implementation work order, not a statement that the interfaces are separate systems.

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

The three demonstrations should use the same underlying resource/session model rather than three duplicated implementations.

## Final instruction to the coding AI

Do not decide what the project “really is” before reading its history.

**Preserve the possibility before deciding what it is.**

**Reconcile before extending.**

**Preserve the local guide; generalize the interface.**

**One underlying system, multiple replaceable interfaces.**

**Build the smallest modular vertical slice before expanding the system.**

The repository's history tells you why the system exists. The current project documents tell you what has been established. This prompt tells you what the coding AI is currently being asked to build. Workflow archives preserve the path by which those understandings developed.

Build the smallest testable increment that moves the repository toward the demonstrated workflow, while preserving the evidence trail and all meaningful prior work.
