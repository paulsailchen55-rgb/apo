# Design Notes

## 1. Minimal watch philosophy

The preferred device is visually and operationally close to a standard watch. The user should not have to navigate a smartphone-like screen. The primary user interface is speech; the visible display may show only time, date, status indicators, and short confirmation information.

The device should avoid continuous listening at full processing power. A low-power acoustic front end or wake-word detector could activate the main processor only when needed.

## 2. Voice-first secretary interaction

The watch captures the user's speech. Depending on the hardware and network design:

- Local recognition can handle a small command vocabulary, wake phrase, cancellation, confirmation, and digits.
- Remote processing can handle open-ended speech, web-page summarization, questions, mapping requests, and secretary functions.
- A hybrid model is likely: local wake/command recognition with remote language and speech services.

The user should be able to say things such as:

- "Secretary, call my librarian."
- "Read this number back to me."
- "Dial extension 204."
- "Repeat that."
- "Cancel."
- "Where am I?"
- "Give me directions to the library."
- "Emergency."

Sensitive numeric information should be repeated in grouped digits and confirmed before transmission. The service should avoid retaining account numbers by default and should provide clear disclosure when information is being sent to a third party.

## 3. Secretary-side telephony control

The secretary service could handle telephone complexity on the backend:

1. Place the outgoing call.
2. Detect spoken prompts and/or keypad menu requirements.
3. Generate DTMF digits for menu selections.
4. Ask the user for account numbers, PINs, extensions, or other required numeric information.
5. Convert confirmed spoken digits into DTMF signals or other supported input.
6. Repeat, correct, or cancel entries when the user requests it.

This requires a telephony provider or controlled call path that permits the service to send DTMF. Not every ordinary phone connection or voice assistant provides this capability.

## 4. Rotating 12-position bezel concept

A rotating bezel could be a tactile fallback input without turning the watch into a visible keypad. The bezel could have twelve indexed positions, potentially corresponding to 1–12, with a fixed marker.

Possible interaction:

- Rotate the bezel to a number.
- A detent or haptic click indicates each position.
- Pause briefly to select the highlighted number.
- The watch speaks the selected digit or number.
- A spoken command such as "confirm" commits the entry.
- A reverse rotation, long pause, or spoken "cancel" removes the pending entry.

Possible implementations:

- Mechanical indexed ring with a magnetic or optical position sensor.
- Rotary encoder with detents.
- A ring with one or more tactile reference markers.
- A 12-position ring that is interpreted contextually rather than permanently representing a telephone keypad.

Advantages:

- Works without a screen or touchscreen.
- Offers a tactile fallback in noisy environments or when speech recognition fails.
- Can be used for numbers, menu choices, and short confirmations.
- May preserve the ordinary-watch appearance.

Challenges:

- A twelve-position ring is not a complete telephone keypad.
- Entering long numbers one digit at a time may be slow.
- Users need reliable feedback for the current position.
- A rotary ring can be accidentally moved.
- The system needs a clear distinction between selecting a number and committing it.
- Number entry must be designed for people with limited dexterity, vision, hearing, or speech.

A practical compromise is to use the bezel primarily for short selections and corrections, while the secretary handles long numbers through speech and confirmation.

## 5. Power and data efficiency

The device should avoid continuous broadband audio streaming when possible. A possible hierarchy is:

1. Local wake-word detection.
2. Local recognition of a small command grammar and digits.
3. Send compact command packets or text rather than continuous audio.
4. Use remote speech recognition only for open-ended speech when necessary.
5. Receive text and synthesize speech locally if feasible, or receive compressed speech audio from the service.

The phrase "only sending text" must be defined carefully. If speech recognition and synthesis happen remotely, audio may still be transmitted at some stages. If the watch sends text and receives synthesized speech audio, it still uses packet data, although likely far less than a continuous two-way voice call depending on implementation.

A useful target is **event-driven, low-volume data use**, not zero data. Battery life depends on modem active time, signal quality, transmission power, processor workload, microphone operation, speaker volume, display type, and frequency of interaction.

## 6. Location controls

Location should be separated into distinct capabilities:

- GNSS/GPS receiver state.
- Cellular network visibility.
- Wi-Fi or other positioning sources.
- Location transmission to the secretary.
- Emergency-service location delivery.

A hardware-controlled GNSS switch could disconnect GNSS power or its signal path. A physical position, LED, or audible chime could indicate the state. The hardware should provide a trustworthy status signal rather than relying only on an application setting.

The user-facing status should be explicit:

- "GPS on."
- "GPS off. Cellular network visibility may remain active."
- "Location shared with secretary."
- "Location sharing stopped."
- "Emergency location procedure active."

A carrier may know the serving cell and other radio-network information even when the watch's GNSS receiver is disabled. The secretary cannot automatically receive carrier-derived location unless the carrier or network provider offers an authorized interface.

## 7. Emergency operation

The 911 function must be treated as a separate safety-critical subsystem. It needs actual supported voice calling, emergency routing, location handling, device certification, testing, and carrier compatibility.

The design must define:

- How emergency mode is activated.
- How accidental activation is prevented without creating dangerous delay.
- Whether a physical GPS-off setting can be overridden during emergency operation.
- What location information is sent and to whom.
- What happens when data service is unavailable.
- What happens when cellular capacity is congested.
- How the user is informed of call connection, failure, or uncertainty.

An AI secretary may help initiate or support an emergency workflow, but it must not be treated as a substitute for a properly engineered and certified 911 pathway.

## 8. Voice rendering and identity

The desired interaction may use synthesized speech so the user experiences a continuous conversational interface. If the system renders another person's voice characteristics, it requires explicit consent, identity verification, anti-impersonation safeguards, and clear disclosure. A safe default is a neutral synthesized voice rather than an unrestricted imitation of another person.

## 9. Preliminary design position

The strongest initial architecture is likely:

- Standard-watch exterior.
- Low-power microphone and wake detection.
- Small local command vocabulary.
- Optional tactile rotary bezel for short numeric input.
- Remote AI secretary for complex language, web research, mapping, and telephony control.
- Text-first service protocol.
- Separate certified emergency voice capability.
- Hardware-verifiable GNSS control and transparent network-location disclosure.
