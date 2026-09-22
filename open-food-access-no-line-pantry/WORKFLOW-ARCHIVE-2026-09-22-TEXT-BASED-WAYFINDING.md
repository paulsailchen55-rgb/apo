# Workflow Archive — 2026-09-22 — Text-Based Wayfinding

## Status

**PROPOSED / NOT IMPLEMENTED**

This archive records a shared capability identified during the food-access design discussion. It is not a completed navigation service, validated routing engine, or guarantee of exact directions.

## Core understanding

The food-access service should not be treated as a conventional mapping application. From the user's perspective, it is a **text- and voice-based instruction service**:

1. The person provides a starting point in ordinary language, such as a cross street, address, landmark, or visible house number.
2. The person provides a destination or asks for an authorized food-access point.
3. A backend uses address and street-network data to calculate a route.
4. The service returns one concise message containing specific walking or driving instructions.
5. The message may optionally be read aloud by a voice interface.

The person should not be required to install a mapping app, open a map display, send a photograph, share live location, enable continuous GPS, or maintain a permanent commercial account.

## Proposed functional requirement

> The system shall accept a user-provided origin (cross street, address, landmark, or spoken description), calculate a route using available backend data, and return concise text or voice directions without requiring continuous GPS, map display, or persistent movement tracking.

## Food-access-specific requirements

Directions should distinguish, where known:

- walking versus driving access;
- public entrance, permitted pickup point, or publicly facing box;
- operating hours and access windows;
- host-provided restrictions and boundaries;
- forecast, reported, inspected, or confirmed availability;
- after-dark or safety restrictions;
- uncertainty caused by changing roads, sidewalks, entrances, construction, or inventory.

The service must not direct a person to trespass, enter private property, harvest without authorization, or assume that a listed resource remains available after its last confirmation.

## Privacy boundary

GPS-free does not mean that no location information is processed. The user-provided origin and destination are transmitted to the service for the specific request. The design should minimize exposure through short-lived request records, explicit retention and deletion rules, no advertising trackers, no continuous location collection, and no unnecessary personal movement history.

Telecommunications providers may retain network metadata outside the application's control. The service must not describe the system as completely invisible to carriers or networks.

## Reliability and uncertainty

The service should say when a route is based on incomplete or stale information. "Specific directions" means actionable route steps, not a promise that every instruction is permanently exact. The system should support user correction, such as:

- "That entrance is closed."
- "I am at the other corner."
- "I am walking, not driving."
- "I cannot use stairs."
- "Read the next step again."

## Relationship to shared capability

This capability is also archived in the `emergency-ai-secretary-watch/` project because the same backend pattern may support a person who speaks or texts their current location and receives short instructions through a phone or watch. Each project retains its own safety and access requirements.

## Evidence labels

- **KNOWN:** The user wants instructions delivered through text or speech rather than a required map interface or continuous GPS.
- **PROPOSED:** Backend geocoding, routing, concise instruction generation, user correction, and privacy-minimized retention.
- **UNKNOWN:** The exact routing data source, coverage, accessibility metadata, operating cost, and accuracy in changing local conditions.
- **NOT IMPLEMENTED:** No production service, route engine, data integration, or field validation is included by this archive.

## Open questions

1. Which open and inspectable street/address datasets can support the service?
2. How should the system handle ambiguous intersections, incomplete addresses, and landmarks?
3. How can accessible routes be requested without collecting unnecessary sensitive information?
4. How should one-message length limits be handled while preserving safety-critical steps?
5. What deletion schedule applies to origin, destination, and route-request records?
6. How should the system report route confidence and changing access conditions?
