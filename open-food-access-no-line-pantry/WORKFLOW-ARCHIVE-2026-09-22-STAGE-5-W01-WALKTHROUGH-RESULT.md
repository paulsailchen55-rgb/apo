# Workflow Archive — Stage 5 — W01 Walkthrough Result

**Date:** 2026-09-22  
**Project:** Open Food Access / No-Line Pantry  
**Status:** TESTED in conversational tabletop practice; not production-tested  
**Evidence labels:**
- **KNOWN:** The walkthrough was completed through an explicit end-session choice.
- **TESTED:** A fictional scenario was taken from menu selection through location description, travel-capability selection, access-information review, and session termination.
- **PROPOSED:** The response rules and fictional resource behavior.
- **UNKNOWN:** Actual resource verification, live availability, route feasibility, and real user comprehension.

## Scenario

A person is downtown on Pacific Street, sitting on a bench near Santa Cruz Coffee Roasting Café. They want the closest authorized food-access location and report that they can walk a few blocks.

## Walkthrough sequence

1. User selected `1` — choose the closest location.
2. User described the landmark in natural language.
3. System asked for a more specific landmark and accepted the café reference.
4. User selected `1` — find the closest location.
5. System requested confirmation; user pressed `#`.
6. Prototype presented a fictional resource.
7. User selected `1` — check whether they can get there.
8. User selected `1` — can walk a few blocks.
9. User selected `1` — check whether the location is open and accepting people.
10. System correctly stated that the fictional location could not be verified.
11. User selected `3` — learn what information is needed before visiting.
12. User selected `5` — end the practice session.

## Findings

### Finding 1 — Verification must precede search-result presentation

The prototype introduced a fictional resource before verification. It later disclosed that the resource was fictional and unverified. This is an identified design weakness.

**Required correction:** A production workflow must not present an unverified or fictional resource as a search result. If practice data is used, label it before the user could mistake it for a real destination.

### Finding 2 — The system appropriately avoided false certainty at the later step

The response explicitly stated that hours and eligibility could not be verified and did not direct the person to the fictional location as if it were real.

### Finding 3 — Location-first discovery remained intact

The system did not require the person to disclose food preferences, immigration status, income, or personal history before beginning location-based discovery.

### Finding 4 — Access capability was considered before route guidance

The walkthrough asked about walking capacity and then moved to operational access information. This remains a proposed interaction pattern requiring broader testing.

## Minimal test record

| Field | Result |
|---|---|
| Scenario ID | W01 |
| Test case ID | W01-E2E-01 |
| Input | Fictional landmark, keypad selections, confirmation, and end-session choice |
| Expected behavior | Preserve context, ask one actionable question, avoid unnecessary sensitive questions, avoid false certainty, provide an endpoint |
| Response summary | Complete fictional journey; later verification disclosure corrected an earlier presentation problem |
| Result category | PARTIAL — flow completed, verification ordering needs correction |
| Corrective note | Verify and label resource data before presenting any destination as a search result |

## Next waypoint

Update the practice implementation so fictional or unverified resources are clearly marked before presentation, then repeat W01 and test a second scenario involving ambiguous location information or an access barrier.
