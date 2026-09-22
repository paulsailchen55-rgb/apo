# Workflow Archive — 2026-09-22
## Stage 2 Waypoint: Access Routing and Assistance

**Project:** `open-food-access-no-line-pantry/`

**Status:** WAYPOINT REACHED — provisional design approval; further testing required

## Purpose

Expedite the tabletop test by grouping related branches. The user provisionally approves the current direction and will review the archive later. This document records the current design without treating tabletop assumptions as real-world validation.

## Operating Method Going Forward

- Test related options as grouped pathways rather than one option at a time.
- Continue automatically through ordinary design decisions.
- Pause at meaningful waypoints, contradictions, safety concerns, or decisions requiring explicit user choice.
- Preserve evidence labels: KNOWN, CALCULATED, TESTED, PROPOSED, SPECULATIVE, UNKNOWN.
- Do not claim that a tabletop pass equals a live test or verified service availability.

## Consolidated Design Decisions

### A. Five constructive paths

Where appropriate, the service may present five simple ways forward. Five is a usability pattern, not a mandatory limit. Users may choose a number or respond naturally in their own words.

The paths should support clarification, comparison, assistance, more information, and return to a broader menu. They should not create a dead end.

### B. Location uncertainty

The system should use landmarks, businesses, transit stops, cross streets, neighborhood language, and other local descriptions as clues. Interpretations remain hypotheses until corroborated by geographic information or user confirmation.

The system must not invent exact location, proximity, availability, or arrival.

### C. Access capability

Food access must account for the complete journey:

- reaching the resource;
- entering and collecting food;
- carrying or transporting food back;
- obtaining a cart, bag, smaller quantity, or other adaptation;
- arranging a helper, proxy pickup, volunteer collection, or delivery.

A walking route alone is not a successful access plan.

### D. Assisted access fork

When the person cannot collect food independently, the system should offer grouped pathways:

1. A known person can collect the food.
2. A volunteer or community helper may assist.
3. An organization may deliver.
4. The selected location may allow proxy pickup.
5. The person is unsure and needs help identifying the practical pathway.

The system must verify actual service availability, geographic coverage, scheduling, eligibility, and contact details before presenting them as reliable.

### E. Registration and documentation

The service should report location-specific requirements, including sign-up, walk-in access, identification, documentation alternatives, and proxy pickup rules. It should not presume immigration status or ask identity questions that are not necessary for the immediate access decision.

### F. Information fields for resource records

Each resource record should eventually support:

- location and service area;
- hours and verification date;
- sign-up or walk-in status;
- identification/documentation requirements;
- delivery availability;
- proxy pickup policy;
- volunteer or community assistance;
- contact methods and separate assistance numbers;
- scheduling requirements;
- quantity or carrying considerations;
- accessibility barriers;
- backup options;
- source and provenance.

Unknown information must be marked unknown rather than filled with assumptions.

## Grouped Tabletop Assessment

### Clarification and discovery

Result: PROPOSED — acceptable for continued testing. The script asks for only the next useful clue, provides alternatives, and avoids false precision.

### Nearby options

Result: PROPOSED — acceptable for continued testing. The script presents a small set of possible resources and distinguishes confirmed information from uncertainty.

### Travel and return feasibility

Result: PROPOSED — acceptable for continued testing. Carrying capacity and the return journey are treated as central access conditions.

### Assisted delivery and collection

Result: PROPOSED — acceptable for continued testing. The service switches from ordinary navigation to an assistance pathway when the person cannot collect food independently.

### Documentation and registration

Result: PROPOSED — requires location-level verification. The system should explain requirements without unnecessary identity screening or unsupported assumptions.

## Current Waypoint

The design has moved from basic location finding toward **practical access routing**. The service is not merely a directory or map. It is a decision-and-assistance pathway that helps a person identify a usable next step.

## Next Waypoint Target

Develop and test a grouped resource-response format that shows:

1. what the resource provides;
2. whether sign-up is required;
3. whether identification is required or unknown;
4. whether the person can use proxy pickup;
5. whether delivery or assistance is available;
6. which phone or text contact is appropriate;
7. what to do if the first option fails.

Then test error recovery: unavailable delivery, unanswered phone number, closed entrance, changed destination, or inability to carry the available amount.

## Data and Privacy Boundary

This archive contains fictional tabletop design decisions only. It contains no real user identity, exact movement history, personal phone number, or live eligibility determination. Any pilot involving real people requires separate privacy, consent or notice, minimization, retention, access control, redaction, deletion, and incident-response decisions.
