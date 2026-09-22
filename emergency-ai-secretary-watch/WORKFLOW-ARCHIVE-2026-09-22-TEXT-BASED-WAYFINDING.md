# Workflow Archive — 2026-09-22 — Text-Based Wayfinding

## Status

**PROPOSED / NOT IMPLEMENTED**

This archive records a shared capability for the Emergency AI Secretary Watch and One-Number AI Secretary service. It is a concept record, not a certified navigation or emergency-safety implementation.

## Core concept

The user should be able to speak or text a location description such as:

- "I'm at the corner of X and Y."
- "I'm at this block and I can see house number Z."
- "I'm near this landmark."

The secretary service then asks for or receives a destination, calculates a route on the backend, and returns short step-by-step instructions through text and, when requested, synthesized speech. The watch or phone does not need to display a map or continuously determine and transmit the user's location.

## Proposed functional requirement

> The system shall accept a user-provided origin (cross street, address, landmark, or spoken description), calculate a route using available backend data, and return concise text or voice directions without requiring continuous GPS, map display, or persistent movement tracking.

## Interaction sequence

1. **Origin intake:** Receive a spoken or typed description of the user's current location.
2. **Clarification:** Resolve ambiguity by asking a short question or requesting a nearby visible address/landmark.
3. **Destination intake:** Receive a destination, saved authorized contact, or food-access resource.
4. **Travel mode:** Confirm walking or driving, and ask for relevant access needs when necessary.
5. **Route calculation:** Use backend street/address data and a routing engine.
6. **Instruction delivery:** Send a concise message and optionally read it aloud.
7. **Correction loop:** Allow the user to say or text that an entrance is closed, the starting corner was mistaken, or the next instruction should be repeated.
8. **Completion:** End the request when the user confirms arrival or stops the interaction.

## Privacy and location modes

GPS-free navigation is not equivalent to tracking-free operation. The service receives the location that the user intentionally supplies for the request. The design should avoid continuous GPS collection, persistent movement history, advertising trackers, and unnecessary retention of origin/destination data.

The watch's own GNSS/GPS control, privacy mode, navigation mode, and emergency mode must remain distinct. Emergency calling and emergency location behavior require separate carrier, regulatory, device, and emergency-services analysis; ordinary text-based routing must not be presented as a substitute for emergency location capability.

The system must also disclose that cellular providers may retain network metadata beyond the application's control and that carrier-network visibility is not the same as precise GPS positioning.

## Output requirements

Instructions should be:

- short enough for text-first delivery;
- readable aloud in a predictable order;
- explicit about turns, crossings, entrances, and destination-side details when known;
- honest about uncertain or stale road, sidewalk, entrance, and landmark data;
- able to pause and repeat the current step;
- usable without a map display.

"Exact instructions" should be treated as a goal for specificity, not a guarantee. The service must communicate uncertainty rather than inventing certainty.

## Shared-service relationship

This capability is shared conceptually with `open-food-access-no-line-pantry/`. The food-access project adds host permission, public access boundaries, operating hours, resource status, and no-trespass requirements. The watch project adds voice interaction, low-bandwidth delivery, tactile fallback, device privacy controls, and separation from emergency operation.

## Evidence labels

- **KNOWN:** The user wants user-declared locations, text-first instructions, optional spoken output, no required map display, and no continuous GPS requirement.
- **PROPOSED:** Backend geocoding and routing, concise instruction generation, correction loops, and short-lived request handling.
- **UNKNOWN:** Routing data provider, offline capability, accessibility coverage, network failure behavior, and measured instruction accuracy.
- **NOT IMPLEMENTED:** No production routing service, hardware integration, emergency certification, or field validation is included by this archive.

## Open questions

1. Which routing and address datasets can be used with inspectable privacy and licensing terms?
2. Can the service operate acceptably during weak or congested cellular connectivity?
3. What is the minimum safe message structure for one instruction at a time?
4. How should the watch indicate that it is speaking, waiting, uncertain, or unable to route?
5. How should users explicitly cancel a route and delete the associated request data?
6. How should emergency mode prevent confusion between ordinary navigation and emergency location workflows?
