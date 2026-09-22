# Workflow Archive — 2026-09-22 — Stage 6: Resource Document Ingestion and Calendar Output

## Purpose

Record the transition from fictional practice resources toward a real resource-data layer for the Open Food Access / No-Line Pantry project.

The immediate lesson from the Stage 5 walkthrough is that the system should not ask a person to evaluate travel capability or continue a conversational path before the system has evaluated whether a resource is actually relevant and actionable at the current day and time.

The next implementation step is therefore **resource data first, conversation second**.

## Core Architecture

**Document → structured resource records → time/location/eligibility evaluation → actionable guidance**

Example:

**People First Free Guide → upload → structured resources → time/day evaluation → user selects service → route → Add to Calendar**

## Document Upload

Authorized resource maintainers should be able to upload source documents such as:

- People First Free Guides
- English and Spanish guides
- veteran-specific resource guides
- flyers
- temporary notices
- closure notices
- updated schedules
- other community resource documents

The upload function is intended for authorized maintainers, not for ordinary food seekers.

The system should preserve the source document and its provenance rather than treating extracted text as an authoritative replacement.

## Structured Resource Record

A resource record should be able to retain, where available:

- resource name
- service type
- address
- landmark or location description
- days of operation
- opening time
- closing time
- holiday exceptions
- temporary closure information
- 24/7 status
- eligibility requirements
- documentation requirements
- walk-in versus appointment requirements
- accessibility/travel information
- language
- source document
- source document version/date
- page or section reference where practical
- extraction confidence
- verification status
- last verified timestamp
- notes about uncertainty or changing information

## Provenance

Extracted information must remain traceable to its source.

A resource record should not silently become more authoritative merely because an AI extracted it.

Where practical, the system should retain:

- source filename or document identifier
- source version/date
- page/section
- extraction timestamp
- extraction confidence
- human/community verification status
- last verification date

## Time-Aware Evaluation

Before presenting a resource as actionable, the system should evaluate:

1. current local day
2. current local time
3. published operating hours
4. known holiday exceptions
5. known temporary closures
6. 24/7 status
7. eligibility
8. documentation requirements
9. walk-in/appointment status
10. service type
11. location

Suggested output states:

- OPEN / ACTIONABLE
- CLOSED / NEXT KNOWN OPENING
- 24/7
- ELIGIBILITY-RESTRICTED
- TEMPORARILY UNAVAILABLE
- UNKNOWN / NEEDS VERIFICATION

**UNKNOWN must never silently become availability.**

A resource with missing or stale hours should be represented as uncertain rather than presented as currently open.

## Location and Travel

A landmark clue is not the same thing as GPS.

The system may use:

- address
- landmark
- intersection
- transit stop
- neighborhood description
- other location clues

When actual location data exists, the system may calculate distance or travel estimates.

Travel capability should be treated as part of the access calculation, not as a gate that prematurely terminates the resource search.

Possible access alternatives include:

- walking
- transit
- bicycle
- cart/bag considerations
- smaller quantity if appropriate
- delivery
- volunteer assistance
- trusted-person or proxy pickup
- other locally authorized assistance

The system should not claim that a person has arrived unless arrival is supported by an appropriate signal such as GPS or an explicit user report.

## Calendar Output

The preferred interoperability target is iCalendar (.ics).

A generated calendar event may include:

- resource name
- selected date
- start time
- end time
- address
- eligibility/reminder information when useful
- source/verification note
- optional route link

User choices should be explicit:

1. Add to calendar
2. Download calendar event
3. Don't add

Recurring services should not automatically become permanent commitments.

The implementation should distinguish:

- one-time selected visit
- recurring reminder based on verified recurring hours
- frequently changing schedule

Calendar entries should be useful without embedding sensitive personal eligibility information unless the person explicitly requests it.

## Verification and Freshness

The system should distinguish information that is:

- verified and current
- verified but potentially stale
- extracted but not yet verified
- temporarily reported unavailable
- unknown

A document date alone does not establish that a resource is currently operating.

Changing schedules require a mechanism for re-verification.

## Evidence Labels

### KNOWN

- Community resource guides can contain resource names, locations, schedules, eligibility information, and service descriptions.
- Source documents can provide provenance for extracted resource information.
- iCalendar (.ics) is an interoperability format for calendar events.
- The practice prototype needs structured resource data before it can realistically test time-aware resource selection.

### CALCULATED

- A resource's actionable state can be calculated from structured hours, the current local day/time, and known exceptions when those inputs are sufficiently complete and trustworthy.
- Distance/travel estimates can be calculated when reliable location data is available.

### TESTED

- The Stage 5 practice walkthrough exposed that asking additional conversational questions before establishing resource availability produces an incorrect flow.
- The prototype demonstrated keypad interaction and recovery behavior, but it did not yet use a real resource-data layer.

### PROPOSED

- Authorized document upload and ingestion.
- Structured resource records with provenance and verification fields.
- Time/day/eligibility evaluation before resource presentation.
- Location-aware access evaluation.
- iCalendar event generation after a person selects an actionable resource.
- A small real-data fixture based on an actual community guide as the next implementation waypoint.

### SPECULATIVE

- Automated extraction may eventually reduce staff data-entry burden.
- AI may assist with identifying schedule changes or conflicts between documents, subject to human verification.

### UNKNOWN

- Extraction accuracy for real-world PDFs, scanned documents, tables, and multilingual content.
- Best verification workflow and authority model.
- How frequently individual resources change their schedules.
- Direct mobile calendar behavior across Android, iOS, Google Calendar, Apple Calendar, and other clients.
- Appropriate confidence thresholds for automatic versus human review.
- How to represent complicated eligibility rules without oversimplifying them.

## Immediate Implementation Waypoint

Stop expanding the fictional conversation flow for the moment.

Build a small, real resource-data fixture from the People First Free Guide, preserving source/version metadata and marking the historical/current verification status clearly.

Then build the evaluator that answers:

**Given a resource record + current local date/time + available location information, is this resource actionable, closed, restricted, temporarily unavailable, 24/7, or unknown?**

Only after that should the conversational interface be connected to the resource layer.

## Design Principle

The system should do the work that can be done before asking the person to do work.

If the system can determine from its own resource data that a location is closed, it should not make the person spend interaction turns discovering that fact.

If the system cannot determine whether a resource is open, it should say so clearly and preserve a useful alternative rather than pretending.

## Relationship to Previous Stages

This stage does not replace previous workflow archives.

It builds the missing foundation beneath them:

- Stage 1 established location-first and keypad/text/voice access.
- Stage 2 established waypoint routing, eligibility comparison, failure recovery, and no-dead-end behavior.
- Stage 3 established minimal button-response behavior and machine-readable testing.
- Stage 4 created the first practice implementation.
- Stage 5 exposed interaction burden and verification-order problems.
- Stage 6 now moves the project toward a real, source-backed resource-data layer.

Existing files remain intact. No duplicate workflow archives should be deleted or merged without explicit approval.
