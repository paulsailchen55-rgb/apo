# Workflow Archive — 2026-09-22
## Stage 2 Waypoint: No-Dead-End Failure Recovery

**Project:** `open-food-access-no-line-pantry/`

**Status:** PROPOSED — grouped tabletop design block; not a live service test

## Objective

Ensure that a failed delivery, pickup, registration, communication, or access pathway does not force the person to restart or abandon the search for food.

The service should preserve relevant context and offer a practical next step.

## Context That Should Be Preserved

Where appropriate, the system retains within the active interaction:

- Approximate or confirmed location clues
- Food-access need
- Walking and carrying capability
- Need for a helper, proxy pickup, or delivery
- Communication limitations, such as inability to make a private phone call
- Requirements already discovered
- Options already considered or ruled out

The system should not retain unnecessary personal information by default.

## Failure-Recovery Rules

When a pathway fails, the system should:

1. State what is known about the failure without blaming the person.
2. Avoid claiming that an unverified service is available.
3. Offer a small number of alternative paths.
4. Keep the user’s prior context so they do not have to repeat everything.
5. Allow the user to return to the main menu, pause, cancel, or change the goal.
6. Explain when a phone call, registration, eligibility check, or human confirmation is required.
7. Provide a clear fallback when no pathway can currently be verified.

## Example Scenario

**Simulated user:**

> “I need delivery, but I cannot make phone calls privately.”

**Proposed response pattern:**

> “We can try another way. I have not confirmed a delivery option that works without a phone call. You can:
>
> **1.** Look for text-based assistance.
>
> **2.** Check whether a trusted person can collect food for you.
>
> **3.** Look for an organization with a different contact method.
>
> **4.** Check whether a nearby location allows an authorized representative to pick up food.
>
> **5.** Return to the main menu or pause here.
>
> I’ll keep the location and access information you already provided while we continue.”

This is a proposed script, not a verified resource response. Actual organizations, phone numbers, eligibility rules, and delivery methods must be confirmed from current location-level information.

## Pass / Fail Criteria

| Criterion | Expected result |
|---|---|
| No blame or shame | PASS if the response treats the barrier as a system/access issue rather than user failure |
| Context preservation | PASS if the user does not need to repeat known information unnecessarily |
| No false promise | PASS if unverified delivery or assistance is not presented as available |
| Alternative pathways | PASS if multiple practical next steps are offered |
| Communication accessibility | PASS if the system considers non-phone alternatives |
| User control | PASS if pause, cancel, main menu, and change-goal options remain available |
| Clear uncertainty | PASS if unknown, unavailable, and needs-verification states are distinguished |
| Data minimization | PASS if only necessary active-session context is retained |

## Evidence Classification

- **KNOWN:** Access barriers can prevent completion even when food resources exist.
- **PROPOSED:** Failure recovery should preserve context and offer alternatives instead of restarting.
- **UNKNOWN:** The availability and reliability of text-based assistance, proxy pickup, volunteer help, and non-phone contact methods vary by location.
- **NOT TESTED:** No real person, real phone number, real delivery request, or real movement data was used.

## Open Questions

- How should the service safely verify that a proposed helper or representative is authorized?
- What is the minimum information needed to search for text-based or non-phone assistance?
- How should the service handle a person who cannot text, speak, or maintain a private conversation?
- When should a human/community assistance handoff be offered?
- How should expired or unverified resource records be displayed?
- What is the safest fallback when no suitable pathway can be confirmed?

## Next Waypoint

Develop a compact, location-level resource record and a grouped eligibility/access comparison flow. Then test a complete journey from initial location clue through resource failure and recovery.
