# Emergency AI Secretary Watch — Chat-Log Archive

## Purpose

This document preserves the exploratory conversation, including rough ideas, discarded directions, unresolved questions, corrections, and design choices. It is intentionally not polished into a final specification. The mess is part of the research record.

## Relationship to other work

This is a distinct project folder in the `apo` archive repository. It is explicitly connected to the **One-Number AI Secretary phone project**. The watch is conceived as a minimal wearable endpoint for that broader secretary service, not necessarily as a replacement for the phone project.

## Core vision

The preferred device resembles an ordinary watch. It should expose very little complexity to the wearer: primarily time and possibly date. The user should be able to ask an AI secretary for information, call organizations or people through the secretary, request web-page summaries, ask follow-up questions, obtain directions, and receive spoken responses.

The watch is intended to be highly efficient and capable of lasting all day. The preferred normal communication path is speech captured by the watch, converted to text, processed remotely by an AI/secretary system, and returned as text or synthesized speech. The user should experience the response as an ongoing voice-like conversation even though the underlying interaction is primarily text/data based.

## Main interaction concept

- The user speaks to the watch.
- The watch captures speech, ideally using low-power local activation and possibly local recognition for a small command vocabulary.
- Speech is converted to text locally or remotely.
- The secretary interprets the request and performs the complicated work.
- The secretary responds through synthesized speech.
- Ordinary communication should not require a conventional voice call.
- A real cellular voice path is retained for 911/emergency calling, subject to carrier, regulatory, location, certification, and reliability requirements.

## Telephone and keypad problem

A major motivation is that many telephone systems still require keypad tones. Users may need to enter:

- Bank account numbers or other numeric identifiers.
- Benefits or food-assistance account numbers.
- Phone numbers.
- Extensions.
- Automated menu choices.
- Verification digits.

Voice recognition alone is unreliable because some automated systems do not accept spoken digits, and some require DTMF keypad signals. The proposed solution is for the secretary service to control the call and generate DTMF tones on the user's behalf.

Example flow:

1. User: “Secretary, call the county benefits office.”
2. Secretary places the call.
3. Automated system says, “Press 2 for benefits.”
4. Secretary detects or is told the required choice and sends DTMF `2`.
5. The system asks for an account number.
6. Secretary asks the user to read the number aloud.
7. Secretary repeats the digits for confirmation.
8. After confirmation, secretary transmits the digits as DTMF or by the appropriate supported input method.

This capability depends on the secretary's telephony provider having control over the call audio/signaling path. It cannot be assumed to work with every ordinary phone connection.

## Optional tactile number entry

The initial preference was to have no screen, keypad, or complicated controls. A possible fallback is a rotating bezel or ring with twelve positions, inspired by watches with directional bezels and old rotary telephone dialers.

Possible behaviors:

- The bezel has a physical marker.
- Rotating the ring selects a number or menu option.
- Pausing at a position loads or selects the value.
- A spoken confirmation can confirm the selected digit.
- The ring could be used for digits, menu choices, or emergency interaction.

This is not yet locked in. Questions include whether twelve positions are efficient for ten digits, whether users can distinguish positions by touch, whether a rotary interaction is faster than speech, how multi-digit numbers would be entered, how accidental movement is prevented, and whether the mechanism undermines the desired ordinary-watch appearance.

The bezel should remain an optional fallback rather than the primary interaction method unless testing demonstrates a clear benefit.

## Voice user interface

The watch needs a voice-user interface (VUI), including a short command grammar. Possible commands include:

- “Wake up” — activate the interaction system.
- “Secretary” — address or connect to the secretary.
- “Repeat” — repeat the last response.
- “Cancel” — cancel the current action.
- “Emergency” — begin an emergency workflow.
- “Battery” — report battery status.
- Spoken digits such as “five” — select a menu item or number.

A spoken digit should not automatically cause a consequential action without confirmation. Misrecognition is possible, especially in noise. Numeric input should use read-back, confirmation, correction, and cancellation.

## Location and privacy concept

The watch may need location services for:

- Emergency location support.
- Mapping and directions.
- Helping the secretary understand where the user is.
- Potentially transmitting location to authorized services.

A key requirement is a physical way to turn location capability on and off, with a state that is externally visible or audibly confirmed. Software should not merely claim that location is off if the relevant hardware remains active.

The design must distinguish:

1. GNSS/GPS location calculated by the device.
2. Cellular network visibility, including the serving cell/tower area.
3. Other positioning methods such as Wi-Fi or Bluetooth location.

Turning GPS/GNSS off does not make a powered cellular modem invisible to the carrier. The carrier may still know the serving cell and may estimate location. A normal text message does not automatically deliver tower coordinates to the secretary. Access to carrier-derived location would require an authorized carrier/network interface or partnership.

Possible physical design:

- A dedicated location switch.
- Hardware-level disconnection or disabling of GNSS power or antenna path.
- Mechanical switch position visible from outside.
- LED, vibration, or chime confirmation.
- Hardware state reporting that is independent of an application setting.

A transparent status could say: “GPS off; cellular network visibility active.”

The emergency policy remains unresolved: whether emergency mode may request or activate GNSS location when the user has physically disabled ordinary location. Any override must be explicit, documented, visible, and tested rather than hidden.

## Network and data philosophy

The desired system should not maintain a continuous high-bandwidth voice stream for ordinary use. Text-first communication is preferred for battery and network efficiency. However, AI processing, speech recognition, and synthesized speech generally require some data transmission unless significant processing is performed locally.

The practical target is therefore likely:

- No continuous broadband audio stream during ordinary secretary use.
- Small, intermittent packets where possible.
- Local wake-word detection and possibly local recognition of a small command vocabulary.
- Remote processing for complex speech recognition, AI reasoning, web retrieval, and speech synthesis.
- A separate, certified cellular voice pathway for 911.

Network capacity is not determined only by the number of bytes in each message. Radio resources, spectrum, signaling load, congestion, backhaul, coverage, priority rules, and operator policies all matter. The secretary backend must also avoid becoming a single bottleneck through redundancy and distributed service design.

## Voice output and voice-call illusion

The desired user experience is a natural spoken interaction. The underlying system may send text to the AI and receive text or speech-generation instructions. Synthesized speech should be clear, low-latency, and power efficient.

Earlier exploration included the possibility of analyzing another person's voice and synthesizing speech that resembles that person when connecting the user to another person. This creates substantial consent, identity, impersonation, privacy, and anti-fraud questions. It should not be treated as a default feature. A safer initial design would use a neutral, clearly synthetic voice or a voice profile explicitly authorized by the speaker.

## Emergency calling

911 must not be treated as merely another AI text workflow. The system needs an actual emergency-capable voice pathway, carrier support, emergency routing, location handling, fallback behavior, certification, testing, and clear failure modes.

Possible separation:

- Normal mode: text/data-based secretary interaction with synthesized speech.
- Emergency mode: approved emergency workflow that can establish a genuine voice call when technically and legally supported.
- Navigation mode: location enabled with user control and clear status.
- Privacy mode: GNSS disabled while cellular network visibility is clearly disclosed.

The emergency interface must account for false activation, speech recognition failure, inability to speak, poor coverage, battery depletion, and the possibility that the AI service is unavailable.

## Processing architecture possibilities

### Local

Local wake-word detection and speech recognition reduce dependence on network connectivity and can reduce audio transmission, but require more processing, memory, power, and hardware complexity.

### Remote

Remote speech recognition and AI processing simplify the watch and allow more capable models, but increase network dependence, latency, privacy exposure, and service availability risk.

### Hybrid

A likely prototype direction is hybrid:

- Low-power local wake-word or activation detection.
- Local recognition for a small set of commands and digits.
- Remote processing for general speech, AI reasoning, web pages, secretary functions, and synthesis.
- Local emergency fallback logic that does not depend entirely on the AI service.

## Prototype progression

1. Simulate the secretary workflow on an Android device or development board.
2. Test wake-word and short-command recognition.
3. Test spoken digits, read-back, correction, and confirmation.
4. Simulate DTMF handling and telephone menu navigation.
5. Measure battery use for microphone standby, local processing, transmission, and audio output.
6. Test a minimal watch-like interface.
7. Investigate cellular modem, VoLTE/911, eSIM, GNSS, and carrier requirements.
8. Conduct emergency reliability and privacy testing before any real-world deployment.

## Open questions preserved

- Is a twelve-position rotary bezel efficient enough for digit entry?
- Should the bezel select digits, menu items, or both?
- Can it remain visually indistinguishable from a conventional watch?
- What is the lowest-power microphone and wake-word architecture?
- Can local recognition handle digits reliably in noisy environments?
- How can the watch confirm that a location switch is physically active or inactive?
- What location information can an actual carrier expose to the secretary service?
- Can the secretary reliably detect automated telephone prompts?
- How should it handle systems that do not expose reliable speech or keypad control?
- How should users securely enter sensitive numbers without exposing them to unnecessary logging?
- What is the emergency behavior when GPS is physically off?
- How can 911 operate if the AI service, data connection, or backend is unavailable?
- How much battery is consumed by synthesized speech compared with streaming voice?
- What cellular technology provides adequate coverage, low power, and genuine emergency calling support?
- What happens when millions of users attempt emergency communication simultaneously?

## Archival note

This file intentionally includes both adopted and rejected ideas, uncertainties, and unfinished reasoning. Future decisions should be recorded with their rationale, alternatives considered, and tests required before the decision is considered locked.
