# Workflow Archive — 2026-09-22
## Stage 2 Tabletop Test 01: Access Capability and Assisted Delivery Fork

**Project:** `open-food-access-no-line-pantry/`

**Status:** IN PROGRESS — tabletop design test; not a real-world pilot

**Evidence classification:**
- KNOWN: A food-access route can fail even when food is available if the person cannot walk, carry the food, enter the location, register, or arrange collection.
- PROPOSED: Treat physical access, carrying capacity, proxy pickup, delivery, and entry requirements as early decision branches.
- UNKNOWN: Which specific organizations offer delivery, volunteer pickup, proxy pickup, carts, bags, or other assistance in each service area; eligibility and documentation rules require location-level verification.
- NOT TESTED: No live user, real movement record, or real resource eligibility decision was used in this tabletop test.

## Purpose

Pause the conversation test before continuing into the assisted-delivery branch and preserve the design decisions developed during Steps 1–5.

The system must help a person reach a practical food-access outcome, not merely identify a place where food exists.

## Decisions Recorded

### 1. Five constructive ways forward

The interaction should often provide five simple paths, where appropriate, so the person is not trapped by one narrow question. The five paths are a design pattern, not an inflexible limit.

The paths should lead toward clarification, assistance, comparison, or another constructive next step rather than a dead end.

### 2. Access capability is an early fork

The system should distinguish among:

1. The person can walk and carry food themselves.
2. The person can walk but needs a cart, bag, smaller amount, or another carrying adaptation.
3. The person needs another person to collect or deliver food.
4. The person needs to know whether registration or identification is required.
5. The person is unsure what kind of assistance is needed.

The person may always respond in natural language instead of selecting a number.

### 3. Carrying and return feasibility

The system must consider the entire journey:

- Can the person reach the location?
- Can they enter, collect, and leave?
- Can they transport the food back to their actual destination?
- Is the amount of food practical to carry?
- Is a cart, bag, smaller package, helper, proxy pickup, or delivery option available?

A route to the resource is not sufficient if the person cannot complete the return journey with the food.

### 4. Assisted collection and delivery

When a person says they need someone else to collect or deliver the food, the system should switch from ordinary walking directions to an assistance pathway.

Potential information fields for each location or service:

- Delivery available: yes / no / unknown
- Volunteer or community pickup available: yes / no / unknown
- Proxy or representative pickup allowed: yes / no / unknown
- Separate assistance phone number
- Text, voice, or other contact method
- Advance scheduling required
- Eligibility or geographic service area
- Maximum quantity or weight limitations
- Fees, if any, clearly distinguished from free food access
- Verification date and source
- Backup pathway if the first assistance option is unavailable

The system must not invent an assistance program, phone number, eligibility rule, or delivery promise.

### 5. Registration and identification requirements

Sign-up and documentation requirements should be presented as location-specific facts, not assumed from a person's identity or appearance.

The service should explain:

- Whether advance registration is required
- Whether walk-in access is available
- Whether identification or other documentation is required
- Whether alternatives exist when a person cannot provide a requested document
- Whether another person may collect food on the user's behalf
- Whether the person should call before traveling

The system should not ask whether someone is an immigrant as a default screening question. It should provide accurate, relevant requirements and allow the person to ask privately about their own circumstances.

## Current Tabletop Test Results

### Step 1 — Initial request

The fictional user says they are near a library, need food, and do not know the street number.

Result: PROPOSED tabletop pass. The response acknowledges the request, avoids false location precision, and offers five ways to clarify the location.

### Step 2 — Location clarification

The fictional user identifies a bus stop and a large grocery store but cannot identify the street.

Result: PROPOSED tabletop pass. The response requests either the bus-stop name or grocery-store name and offers alternatives if the user cannot read signs.

### Step 3 — Nearby discovery preparation

The fictional user identifies the grocery store as FoodMaxx but cannot read the bus-stop number.

Result: PROPOSED tabletop pass. FoodMaxx is treated as a location clue, not as confirmed exact location data.

### Step 4 — Nearby options

The fictional system presents two possible nearby food-access locations and offers comparison, travel feasibility, additional information, or another location clue.

Result: PROPOSED tabletop pass. The system does not claim that either location is definitively closest without confirmation.

### Step 5 — Travel and return feasibility

The fictional user can walk a few blocks but has no cart and may not be able to carry enough food for several days.

Result: PROPOSED tabletop pass. The response recognizes carrying and return feasibility as central and offers five constructive paths.

## Next Test State

The next simulated user selection is:

> “I need someone to collect or deliver the food.”

The next test must determine whether the system:

1. Recognizes assisted collection or delivery as a different service pathway.
2. Avoids simply returning another walking route.
3. Asks only the minimum information needed to identify relevant assistance.
4. Distinguishes delivery, proxy pickup, volunteer collection, and a helper the user already knows.
5. Explains that availability and eligibility must be verified.
6. Provides a fallback when no assistance option is confirmed.
7. Preserves user control and offers five constructive paths when appropriate.

## Data Handling

This archive records design decisions and fictional tabletop behavior only. It does not contain real names, phone numbers, exact personal routes, real-time movement records, or real eligibility determinations.

Any future real-user pilot requires separate privacy and governance decisions covering notice or consent, data minimization, retention and deletion, access control, transcript handling, incident response, and aggregate reporting.

## Open Questions

- Should the first assisted-access question distinguish between a known helper and an organization-provided service?
- How should the system handle a person who cannot make phone calls or speak privately?
- How should urgent food need be represented without making unsupported urgency judgments?
- What minimum location and eligibility data is required before contacting an assistance provider?
- How should stale or unverified delivery information be displayed?
- What happens when every listed option requires a phone call, but the person has no usable phone access?

## Next Action

Continue the tabletop test with the assisted collection and delivery branch, then archive the resulting behavior and pass/fail findings in a separate file rather than overwriting this record.
