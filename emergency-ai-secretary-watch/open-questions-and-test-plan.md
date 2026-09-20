# Open Questions and Test Plan

This document is deliberately unresolved. It identifies questions that must be answered through experiments, user testing, engineering analysis, carrier discussions, or legal/safety review.

## A. Physical form

### Questions

- Can the watch retain a conventional appearance while containing a microphone, speaker, cellular modem, GNSS hardware, battery, antenna, and optional rotary bezel?
- Is an e-ink display necessary, or is a conventional watch display more power-efficient for the limited time/date function?
- Can the bezel be operated by people with limited dexterity, vision, or sensation?
- Can a user feel each position without looking at the watch?
- Is a twelve-position ring confusing because telephone digits are ten-position values?
- Should the ring enter one digit at a time, select a menu item, or scroll through a voice-confirmed list?
- How can the ring prevent accidental input while the wearer moves their wrist?

### Tests

- Measure digit-entry time for speech only, bezel only, and hybrid entry.
- Test with background noise, gloves, wet hands, and limited dexterity.
- Measure accidental activation and correction rates.
- Test whether the device still looks and feels like a standard watch.

## B. Voice interface

### Questions

- Should activation use a wake phrase, a wrist gesture, a bezel action, or a combination?
- How should the watch distinguish a command from surrounding conversation?
- How should it handle homophones and misheard digits?
- Should numbers be grouped into pairs or read one digit at a time?
- How can the system protect account numbers, PINs, benefits identifiers, and other sensitive information?
- Should sensitive numbers be entered locally and transmitted as encrypted structured digits rather than stored as ordinary transcript text?

### Tests

- Test recognition of digits in quiet, traffic, indoor reverberation, and crowded settings.
- Test read-back confirmation and correction phrases.
- Test false wake-ups and missed wake-ups.
- Measure the time and energy cost of local recognition versus remote recognition.

## C. Secretary-controlled telephone systems

### Questions

- Can the telephony provider detect IVR prompts reliably?
- Can it send DTMF digits at the correct time?
- How should the user tell the secretary to press a number when automatic detection fails?
- How should the secretary handle pauses, repeated prompts, invalid entries, CAPTCHA challenges, and human operators?
- What systems prohibit automated access or require direct user participation?
- Can the secretary maintain an auditable record without retaining unnecessary sensitive call content?

### Tests

- Build a simulated IVR with menu choices, extensions, account numbers, retries, and timeouts.
- Measure DTMF reliability across supported telephony providers.
- Test manual user override using spoken commands and optional tactile input.
- Test handoff to a human when automation fails.

## D. Normal text-first communication

### Questions

- What is the smallest useful message protocol between watch and secretary?
- Can the watch send text or structured intent rather than raw audio in most cases?
- How much latency is acceptable before the user thinks the system failed?
- Can speech synthesis stream in short chunks without maintaining a continuous voice call?
- What happens if the user loses coverage while waiting for a response?
- Can the watch cache basic help, battery status, emergency instructions, and a limited contact list locally?

### Tests

- Compare text-only, compressed audio, and continuous audio approaches.
- Measure battery use for standby, uplink, downlink, speaker output, and cellular registration.
- Measure latency and failure recovery under weak signal and congested conditions.
- Test queueing and retry behavior.

## E. Location and privacy

### Questions

- What exact hardware state constitutes GPS/GNSS off?
- Can the device independently verify that GNSS power or antenna access is disabled?
- What indicator is most understandable: mechanical position, LED, chime, vibration, or spoken status?
- How should the watch describe cellular network visibility while GNSS is off?
- Can a carrier provide authorized serving-cell or network-location data to the secretary?
- How accurate is tower-based information in urban, rural, mountainous, and indoor environments?
- Should navigation require an explicit location-on action every time, or should a temporary session be available?
- What is the emergency behavior if location is physically off?

### Tests

- Compare GNSS accuracy with serving-cell estimates in representative environments.
- Test visible and audible switch-state confirmation.
- Verify that software cannot report a false hardware state.
- Test location data minimization, retention, deletion, and access controls.

## F. 911 and emergency operation

### Questions

- Which modem and carrier combinations support the required emergency voice pathway?
- Can 911 function if the AI backend is offline?
- What information is transmitted automatically, and through which authorized emergency mechanism?
- How is location handled when GNSS is unavailable?
- How does the user cancel a false emergency activation?
- What happens when the user cannot speak or the microphone is obstructed?
- What battery reserve is required before the watch warns the user or enters a low-power emergency state?
- What certification and field testing are required before deployment?

### Tests

- Use approved test procedures; do not place unapproved live emergency calls.
- Test emergency behavior under no-data, weak-signal, low-battery, and backend-outage conditions.
- Test spoken and tactile emergency initiation if both are supported.
- Test clear user feedback during dialing, connection, location transmission, and failure.

## G. Voice identity and synthesis

### Questions

- Is a neutral synthetic voice sufficient for the initial version?
- If a connected person’s voice characteristics are used, how is consent collected and verified?
- How does the system prevent impersonation, fraud, and confusion about who is speaking?
- Should the watch announce when speech is synthesized rather than directly transmitted?

### Tests

- Compare intelligibility and latency of neutral voices.
- Evaluate user understanding of the intermediary role.
- Conduct privacy and anti-impersonation review before testing voice likeness.

## H. Scale and resilience

### Questions

- How many devices can be served by one backend region?
- What happens when a large population simultaneously asks for emergency help?
- How much signaling load is generated by always-registered cellular devices?
- Can the service distribute workloads across regions and providers?
- What functions must remain available when the AI service is degraded?

### Tests

- Run load simulations for ordinary traffic and emergency spikes.
- Measure backend queues, retry storms, carrier signaling, and degraded-mode behavior.
- Design rate limits that do not prevent legitimate emergency handling.

## Exit criteria before a real pilot

- Battery performance measured on representative hardware.
- DTMF and IVR workflow demonstrated with an authorized test service.
- Location switch behavior independently verified.
- Privacy model and sensitive-number handling reviewed.
- Emergency pathway validated with appropriate carrier and regulatory partners.
- Accessibility testing completed with diverse users.
- Failure modes documented, including explicit behavior when the secretary cannot respond.
