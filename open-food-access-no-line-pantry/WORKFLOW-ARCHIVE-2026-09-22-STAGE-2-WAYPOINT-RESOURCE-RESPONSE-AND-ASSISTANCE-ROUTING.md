# Workflow Archive — 2026-09-22
## Stage 2 Waypoint: Resource Response and Assistance Routing

**Project:** `open-food-access-no-line-pantry/`

**Status:** PROPOSED — grouped tabletop design block; not live-tested

## Purpose

Define how the service presents a food-access resource so that the person can determine not only whether food exists, but whether they can realistically use the resource and receive the food.

## Core Question

> What is available, can I use it, and how can the food get to me?

## Resource Record — Proposed Fields

### 1. Food

- Food type: groceries, prepared meals, produce, shelf-stable food, or other verified category
- Quantity or practical amount information
- Pickup or delivery format
- Restrictions or limitations, if verified
- Availability date and time

### 2. Access

- Walk-in access: yes / no / unknown
- Advance registration: required / not required / unknown
- Identification or documentation: required / not required / unknown
- Eligibility requirements
- Service area or geographic boundary
- Whether the person should call before traveling

### 3. Collection

- Self-pickup available
- Proxy or representative pickup permitted
- Helper pickup permitted, if different from proxy pickup
- Appointment or scheduling requirement
- Carrying, quantity, or packaging considerations

### 4. Delivery and Assistance

- Organization delivery available: yes / no / unknown
- Volunteer or community delivery available: yes / no / unknown
- Separate assistance phone number or contact method
- Text, voice, online, or in-person request methods
- Scheduling requirements
- Geographic coverage
- Eligibility requirements
- Fees, if any, clearly separated from food availability
- Verification date and source

### 5. Backup Pathway

- Another verified resource nearby
- Another resource with fewer access requirements
- Proxy pickup alternative
- Volunteer or community assistance alternative
- Phone-based help or human referral
- Instructions for what to do if the first contact fails

## Presentation Rules

1. Present essential information first.
2. Do not overwhelm the person with every field at once.
3. Offer more detail as a selectable branch.
4. Never invent phone numbers, service availability, eligibility rules, delivery promises, or identification requirements.
5. Clearly label unknown or unverified information.
6. Preserve user control and allow the person to change the access pathway.
7. Avoid assuming disability, immigration status, family situation, or available helpers.
8. Do not require the person to repeat their entire story when moving between branches.

## Grouped Tabletop Pass/Fail Assumptions

### Proposed PASS conditions

- The system distinguishes food availability from practical access.
- The system distinguishes delivery, volunteer assistance, proxy pickup, and a helper known to the user.
- The system identifies registration and documentation requirements as location-specific facts.
- The system offers a fallback when the first pathway is unavailable.
- The system uses concise first-level information and optional deeper detail.
- The system does not make unsupported promises.
- The system allows natural-language responses alongside keypad choices.

### Remaining UNKNOWN or NOT TESTED conditions

- Accuracy of real location-level resource records
- Freshness and verification process for contact numbers
- Handling of conflicting provider information
- Handling of users without phone access or private calling space
- Response when all known resources require registration
- Response when delivery is limited by service area or capacity
- Accessibility of the presentation for speech, text, low vision, and cognitive load

## Next Grouped Test Block

Test the assistance-routing pathway as a whole:

1. The user requests organizational delivery.
2. The system checks service area and delivery eligibility.
3. The system presents verified contact options.
4. The user cannot make a phone call or has no private place to speak.
5. The system offers text, proxy pickup, helper, community referral, or alternate resource pathways where verified.
6. The system handles no confirmed assistance option without blaming the user or claiming completion.

## Data Handling

This archive contains fictional tabletop design decisions only. No real person, exact personal route, real phone number, or real eligibility determination is included. Real-world implementation requires separate privacy, consent or notice, minimization, retention, access-control, deletion, and incident-response decisions.
