# Workflow Archive — Stage 2 Waypoint: Location Resource Record and Eligibility Comparison

**Date:** 2026-09-22  
**Project:** `open-food-access-no-line-pantry/`  
**Workflow stage:** Stage 2 — Design the AI workflow  
**Status:** PROPOSED; not yet machine-tested

## 1. Objective

Define the smallest useful resource record the AI needs in order to compare nearby food-access pathways without overwhelming the person or requiring them to restart the conversation.

The system should present practical next choices, not expose the full database.

## 2. Compact Resource Record

Each authorized food-access resource should have, where available:

- **Identity:** resource name and resource type.
- **Location:** address, service area, nearby landmarks, and geographic confidence.
- **Food:** general food offered, quantity or limits, and whether selection is fixed or user-chosen.
- **Access method:** walk-in, appointment, registration, referral, order-first, pickup, delivery, or other.
- **Eligibility:** who may use the service and any location-specific requirements.
- **Documentation:** ID, proof of address, registration, or other requirements, marked `REQUIRED`, `NOT REQUIRED`, or `UNKNOWN`.
- **Collection:** user pickup, helper pickup, authorized representative pickup, or restrictions.
- **Delivery:** delivery availability, service area, scheduling, volunteer support, and contact method.
- **Communication:** text, phone, web, in-person, interpreter/language support, or `UNKNOWN`.
- **Time:** hours, appointment windows, order deadlines, and freshness of the information.
- **Physical access:** stairs, slopes, entrance conditions, distance from transit, carrying considerations, and unknowns.
- **Verification:** source, verification date, confidence, and responsible reviewer where applicable.
- **Fallbacks:** other nearby resources or alternate access pathways.

## 3. Evidence Handling

The AI must not guess about eligibility, documentation, delivery, or accessibility.

Use explicit states:

- `KNOWN` — supported by a reliable current source or confirmed interaction.
- `CALCULATED` — derived from stated rules or geographic calculations.
- `TESTED` — demonstrated in a documented test.
- `PROPOSED` — design suggestion not yet verified.
- `SPECULATIVE` — possible but weakly supported.
- `UNKNOWN` — not established.

Every time-sensitive or policy-sensitive field should include a verification date when possible. If the information is unknown or outdated, the person should be told that verification is needed rather than receiving a confident answer.

## 4. Person-Facing Comparison

The system should show a small set of relevant options, using plain language. Possible comparison paths include:

1. **Closest place** — prioritize geographic nearness.
2. **Easiest access** — consider registration, documentation, entrance, and travel barriers.
3. **Someone else can collect** — show proxy or helper-pickup possibilities.
4. **Delivery or assistance** — show verified delivery or volunteer pathways, with limitations clearly stated.
5. **More information or another option** — allow details, comparison, a new clue, main menu, pause, or cancellation.

These are candidate labels and must be tested for comprehension, language accessibility, and keypad/voice use.

## 5. Comparison Rules

- Start with nearby authorized resources.
- Expand the geographic search only when necessary or requested.
- Do not rank a resource as usable solely because it is close.
- Consider route feasibility, return/carrying feasibility, and access feasibility separately.
- Surface the smallest decision needed next.
- Preserve the person's existing location clues, needs, capability limits, and chosen pathway.
- Explain requirements before directing the person to travel when those requirements are known.
- If a requirement cannot be verified, label it `UNKNOWN` and offer a verification or fallback route.
- Do not require a person to disclose a diagnosis, immigration status, or other unnecessary personal information merely to explore options.
- Allow the person to ask privately about requirements and to change or withdraw from a pathway.

## 6. Example Minimal Response

> I found two nearby options.
>
> **1. Community pantry:** closer; pickup; registration requirement is unknown.
>
> **2. Food delivery program:** farther from you; delivery may be available; eligibility must be verified.
>
> Reply **1** or **2**. You can also say **3** to compare access, **4** for more information, or **5** for another way forward.

The exact wording and key assignments remain `PROPOSED` until tested.

## 7. Acceptance Criteria for the Next Test

A design passes this waypoint when:

- The record contains enough information to avoid misleading the person.
- Unknown requirements are visibly preserved rather than guessed.
- The person receives no more than a small, understandable set of choices.
- The comparison includes practical access, not distance alone.
- The person can request details, correct information, change direction, pause, or cancel.
- The AI does not claim delivery, eligibility, or accessibility without support.
- The same context can be carried into a fallback pathway without restarting.

## 8. Open Questions

- Which data sources can verify each field and how often should they be refreshed?
- How should conflicting information from providers be displayed?
- What minimum accessibility information is required before giving route instructions?
- Which keypad functions should be assigned to `*`, `#`, and `0`?
- How should the system handle languages and local vernacular in resource names and eligibility questions?
- What information can be shown publicly, and what must be kept private?

## 9. Next Step

Proceed to Stage 2 Step 7: run one end-to-end tabletop test from the initial location clue through resource comparison, access limitation, failure, and recovery. Record pass/fail/partial/blocked results and revise only the defects revealed by the test.
