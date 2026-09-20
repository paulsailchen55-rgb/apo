# Emergency AI Secretary Watch

## Archive status

Research concept and preliminary design archive. This is not yet a validated hardware specification, certified emergency device, or production implementation.

## Relationship to another project

This project is a distinct wearable-device concept connected to the **One-Number AI Secretary phone project**. The secretary service is the shared backend/service concept; this folder focuses on the watch interface, power efficiency, tactile fallback input, location privacy, and emergency operation.

## Core concept

A minimal, ordinary-looking watch that provides:

- Time and possibly date as its primary visible functions.
- Voice-first access to an AI secretary.
- Text-first communication between the watch and the secretary service.
- Synthesized speech returned to the user so the interaction feels conversational.
- Secretary-side handling of telephone numbers, extensions, automated menus, DTMF digits, and other telephony complexity.
- A genuine cellular voice pathway for 911, designed and tested separately from ordinary AI interaction.
- A physical and verifiable way to control the watch's own GNSS/GPS capability.
- Clear disclosure that GPS being off does not necessarily prevent cellular-network visibility.

## Design principle

The watch should remain simple for the user. Complexity should be moved into the secretary service, while safety-critical functions must remain explicit, independently testable, and honest about their limitations.

## Initial design questions

1. How can the watch recognize short commands locally while keeping power consumption low?
2. Can a rotating 12-position bezel provide efficient tactile number entry without making the watch feel like a conventional phone?
3. How should the secretary transmit DTMF digits and extensions during calls?
4. What information can be sent through a carrier about serving-cell location, and under what authorization?
5. How can the user physically disable and re-enable GNSS/GPS, with an externally visible or audible state indication?
6. How should privacy mode, navigation mode, and emergency mode differ?
7. What cellular technology and service arrangement can support long battery life, low data volume, and a reliable 911 pathway?
8. How can the service remain usable during major emergencies when cellular networks and backend services may be congested?

## Important constraints

- A text-first AI service still requires some packet data unless speech recognition, language processing, and speech synthesis are performed locally.
- The goal is therefore minimal and event-driven data use, not literally zero data.
- Carrier network location cannot be treated as equivalent to precise GPS coordinates.
- 911 functionality requires carrier, regulatory, emergency-services, location, and device-certification work; it cannot be assumed from an ordinary AI data connection.
- Voice imitation or speaker-like synthesis requires explicit privacy, consent, authentication, and anti-impersonation safeguards.

## Suggested future documents

- `design-notes.md` — interface, bezel, power, location, and emergency design considerations.
- `interaction-state-machine.md` — detailed voice and tactile interaction states.
- `open-research-questions.md` — unresolved technical, regulatory, and operational questions.
