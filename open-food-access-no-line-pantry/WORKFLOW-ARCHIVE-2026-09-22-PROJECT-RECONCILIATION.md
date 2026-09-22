# Project Reconciliation — 2026-09-22

## Status

**KNOWN / ARCHIVE RECONCILIATION** — This records the project state after comparing existing files with recovered conversation material and the Stage 6 direction.

## Purpose

The project has accumulated several valid layers: food-access problems, low-barrier interaction design, wayfinding, community access networks, seasonal information, privacy, verification, and calendar output.

This reconciliation prevents two errors: losing an important idea because it existed only in conversation, and forcing distinct ideas into one implementation before their relationship is understood.

No existing files are deleted, merged, or renamed by this reconciliation.

## Already represented

Existing files and workflow archives adequately represent:

- free/open-source, low-barrier food access;
- SMS/keypad-first interaction with optional voice and web;
- location-first access using landmarks and human-readable clues;
- cultural/vernacular wayfinding;
- continuing movement, backtracking, recovery, and no-dead-end behavior;
- access capability and assisted-delivery considerations;
- community food-access networks;
- time-aware and permission-aware routing;
- harvest/seasonal information and temporary notifications;
- forecast versus inspection versus confirmed availability;
- privacy minimization and temporary permissions;
- cognitive-load research and interaction testing;
- calendar output and recurring-pattern handling;
- separate biblical foodway interpretation;
- earlier-conversation recovery and provenance preservation.

These remain separate documents where their scope differs.

## Recovered material that changes implementation direction

The most important recovered insight is a change in implementation order.

**The system should do the information work before asking the food seeker to do work that the system can already do.**

Bad sequence:

location → select unchecked resource → ask whether person can walk there → discover whether it is open

Preferred sequence:

location clue → identify candidate resources → verify status against day/time/eligibility/access conditions → calculate practical access options → present useful next actions

Travel capability remains relevant, but it is part of an access calculation rather than an isolated gate.

## Recovered origin problem

This project did not originate as a generic pantry directory. Earlier material identified concrete access failures and waste:

- unsuitable or spoiled food;
- food a person could not use;
- predetermined bags that did not fit actual needs;
- avoidable waste;
- administrative friction;
- address or ZIP-code barriers;
- concerns about unnecessary tracking or surveillance;
- lack of meaningful food choice;
- the difference between receiving a bag and actually obtaining useful food.

These are user-originated observations and concerns, not universal claims about every food program.

## Resource data is now the primary implementation foundation

Working pipeline:

**Source document or authorized resource input** → **structured resource record** → **provenance and verification** → **day/time/eligibility evaluation** → **location and practical-access calculation** → **actionable result** → **optional calendar event**

The resource record is now the central object connecting the earlier conversation work.

## Minimum resource record

The first record should be capable of representing:

- stable internal resource ID;
- provider/resource name;
- service type;
- address or authorized general location;
- landmark/location clues;
- service days and start/end times;
- holiday or temporary closure information when known;
- 24/7 status when applicable;
- eligibility;
- documentation requirements;
- walk-in/appointment requirement;
- quantity/inventory information when available;
- food categories when available;
- accessibility/travel notes when available;
- language availability;
- source document and source date/version;
- page or section where practical;
- extraction confidence;
- verification status;
- last verified timestamp;
- temporary expiration/withdrawal status.

A resource may be known but not currently actionable. Unknown information must remain unknown.

## Operational status

The evaluator should distinguish at least:

- **OPEN / ACTIONABLE**
- **CLOSED / NEXT KNOWN OPENING**
- **24/7**
- **ELIGIBILITY-RESTRICTED**
- **TEMPORARILY UNAVAILABLE**
- **UNKNOWN / NEEDS VERIFICATION**

A stale source must not silently become a current availability claim.

## Travel and access

“Can I walk a few blocks?” is too narrow. Practical access can depend on walking distance/time, mobility, carrying capacity, food quantity, a cart or bag, transit, bicycle or other mobility, delivery, volunteer assistance, trusted-person or proxy pickup, appointment timing, return-trip feasibility, and destination accessibility.

Ask a travel question only when its answer materially changes the available path and cannot reasonably be derived from known information.

## Document ingestion

Authorized maintainers may eventually upload food-access guides, English/Spanish guides, veteran-specific guides, flyers, schedules, and temporary notices.

The document is evidence/provenance input, not automatically truth merely because it was uploaded. Extraction should preserve source/version/date and produce structured records with confidence and verification state.

## People First guide

The People First of Santa Cruz County Free Guide is a useful first real-world fixture. A guide version found during research was dated January 19, 2025. That historical version must not be presented as September 2026 current availability without current verification.

The first fixture should therefore preserve source/version/date and keep current verification separate.

## Distinct but connected pathways

Seasonal harvest intelligence is not the same as ordinary pantry availability. Preserve distinctions among pantry/service schedule, community meal, prepared food, garden distribution, seasonal harvest, temporary food box, forecast, and confirmed availability.

These may share an evaluator, but their evidence and verification rules differ.

## Cognitive-load findings

Existing numeric interaction targets remain engineering hypotheses, not universal scientific limits. Keep one meaningful action per prompt, early useful orientation, correction/recovery, no unverified resource presented as real/available, and a clear outcome or limitation before unnecessary conversation length.

## Evidence labels

**KNOWN / CALCULATED / TESTED / PROPOSED / SPECULATIVE / UNKNOWN** remain the project evidence categories.

When a proposal becomes tested, record that transition rather than silently rewriting history.

## Current implementation boundary

Do not begin with another conversational walkthrough. Begin with:

1. a small real resource fixture;
2. a resource-record schema;
3. a status/time evaluator;
4. a simple location/access candidate calculation;
5. a concise actionable response format;
6. tests using known and intentionally unknown fields.

Only then connect the existing practice interface to real resource records.

## Reconciliation result

The project is not missing one giant feature. It is missing a reliable **resource-data foundation** that lets the already-developed interaction concepts operate on real, verified information.

That is the next implementation waypoint.

## Provenance

This is a snapshot of the project state on 2026-09-22, incorporating recovered conversation material and comparison with existing APO files. It does not claim that every historical conversation line is available.
