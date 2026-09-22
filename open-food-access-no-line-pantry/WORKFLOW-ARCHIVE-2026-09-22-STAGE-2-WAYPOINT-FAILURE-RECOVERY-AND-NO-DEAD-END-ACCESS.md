# Workflow Archive — 2026-09-22
## Stage 2 Waypoint: Failure Recovery and No-Dead-End Access

**Project:** `open-food-access-no-line-pantry/`

**Status:** PROPOSED — archived design block; not tested with real users or live service data

## Purpose

Define how the food-access service responds when the first pathway is unavailable, unsuitable, inaccessible, or unsafe to complete.

The system should not treat a failed route, unavailable delivery option, inability to make a private phone call, or inability to carry food as the end of the person's journey.

## Core Principle

> A barrier should trigger a constructive next pathway, not a dead end.

The service must preserve the user's progress, avoid requiring the person to repeat their entire situation, and provide a small number of practical alternatives.

## Scenario Used

The fictional user says:

> “I need delivery, but I can't make phone calls privately.”

## Proposed System Behavior

The system should acknowledge the constraint without demanding unnecessary personal explanation. It should not simply provide a phone number and stop.

It should search or present verified alternatives, such as:

1. Text-based assistance, if available.
2. A helper or authorized representative.
3. A community referral or volunteer pathway.
4. Another food resource with a different access method.
5. A way to pause, return later, or continue from the main menu.

The system must label each option accurately as confirmed, unconfirmed, unavailable, or requiring verification.

## Failure-Recovery Menu Pattern

A possible five-choice response is:

1. Find a text-based or online contact method.
2. Find a helper, volunteer, or authorized representative pathway.
3. Find another organization with a different access method.
4. Ask for help understanding the available requirements.
5. Pause, return to the main menu, or continue later.

The five-choice pattern is flexible. The system may reduce or alter choices when fewer options are relevant, while preserving user control and plain-language navigation.

## Requirements

### Preserve progress

- Keep the already established location clues and access constraints within the current interaction when appropriate.
- Do not force the user to repeat the entire story after every failed option.
- Let the user correct, replace, or remove prior information.

### Avoid false promises

- Do not claim that delivery, volunteers, proxy pickup, text service, or online contact exists without verification.
- Do not invent phone numbers, eligibility rules, service areas, hours, or delivery commitments.
- Clearly identify information that is stale, incomplete, or unknown.

### Protect privacy and dignity

- Do not require the person to disclose why they cannot make a private call unless that information is necessary and voluntarily offered.
- Offer text-based or other low-exposure options when verified.
- Avoid assuming disability, illness, immigration status, housing status, or family support.
- Explain actual service requirements without using identity-based assumptions.

### Maintain accessibility

- Keep choices short enough to read or hear.
- Support keypad selection, speech, and natural-language responses where available.
- Offer repeat, shorter wording, more detail, translation, pause, cancel, and main-menu controls.
- Avoid making a person navigate a long list of organizations before identifying the relevant access method.

## Pass/Fail Criteria for Future Tabletop Testing

| Criterion | Expected result |
|---|---|
| Recognizes the stated barrier | PASS if the system responds to privacy/call limitations directly. |
| Does not stop at a phone number | PASS if at least one alternative pathway is offered or the lack of alternatives is explained honestly. |
| Preserves prior information | PASS if the user does not need to repeat established location and access facts unnecessarily. |
| Avoids invented services | PASS if every real-world service claim is verified or marked unknown. |
| Offers constructive choices | PASS if the user receives a small, understandable set of next steps. |
| Preserves user control | PASS if the user can ask for help, return, pause, cancel, or change the destination. |
| Protects privacy | PASS if the system does not require unnecessary sensitive disclosure. |
| Handles no confirmed option | PASS if the system explains the limitation and provides a safe fallback rather than pretending success. |

## Evidence Classification

- **KNOWN:** Access barriers can prevent a person from using an otherwise available food resource.
- **PROPOSED:** Failure recovery should be a core workflow capability rather than an exception added later.
- **UNKNOWN:** The actual availability, capacity, eligibility, and contact methods of assistance providers vary by location and require verification.
- **NOT TESTED:** This is a fictional tabletop design block, not a live service test.

## Open Questions

- How should the system identify whether the user can receive texts safely or privately?
- When should the system offer a trusted helper or proxy pickup pathway?
- What should happen if every verified option requires a voice call?
- How can the system provide a human escalation path without exposing unnecessary personal data?
- How long should an incomplete journey remain available for continuation?
- What minimum information should be retained during a session, and when should it be discarded?

## Next Waypoint

Develop a unified resource record and failure-recovery state model, then test scenarios involving:

- No delivery available.
- No private phone access.
- No eligible proxy pickup.
- Closed or unreachable entrance.
- User cannot carry the food.
- User changes destination or pauses the journey.
