# Interaction State Machine

## Purpose

Define a preliminary interaction model for a watch that has no touchscreen and few or no conventional buttons. The model supports voice commands, tactile fallback input, ordinary secretary interaction, and a distinct emergency pathway.

## States

### S0 — Sleep / watch display

- Displays time and possibly date.
- Main processor and modem remain in low-power state when feasible.
- Low-power acoustic trigger may remain active if the user has enabled it.
- No ordinary location sharing occurs unless separately authorized and required by the service arrangement.

### S1 — Wake / activation

Possible activation methods:

- Spoken wake phrase.
- Rotary bezel movement.
- A future optional tactile or gesture input.

The watch gives a short chime or haptic confirmation. It should not transmit private speech merely because an accidental sound resembles the wake phrase.

### S2 — Listening for command

The watch listens for a constrained command or open-ended request. It should provide a timeout and a spoken or audible prompt if no speech is detected.

Examples:

- Secretary
- Call
- Repeat
- Cancel
- Emergency
- Battery
- Location
- Directions
- Confirm
- Back

### S3 — Local command recognition

Local processing attempts to identify:

- Wake and control commands.
- Digits 0–9.
- Confirm, cancel, repeat, back, and help.
- Emergency keyword or phrase.

If confidence is low, the system asks the user to repeat rather than guessing.

### S4 — Open-ended speech capture

For questions, web-page summaries, mapping, or complex requests:

1. Capture speech.
2. Convert to text locally if possible, or send audio through an authorized secure channel.
3. Send the request to the secretary service.
4. Receive text and/or speech output.

### S5 — Numeric entry

Numeric entry can use speech or the rotary bezel.

Speech flow:

1. User speaks digits or a number.
2. System repeats digits in groups.
3. User says confirm, correct, or cancel.
4. Confirmed value is passed to the secretary service.

Bezel flow:

1. User rotates to a detented position.
2. Watch announces the selected number or gives haptic feedback.
3. Pause selects the pending digit.
4. User repeats for additional digits.
5. User says confirm or uses a defined bezel gesture to commit.

Sensitive numbers should be masked or minimized in logs. The user must be told when a number is about to be transmitted to a third party.

### S6 — Secretary telephony control

The backend may:

- Place a call.
- Detect automated prompts.
- Send DTMF digits.
- Enter extensions.
- Request numeric information from the user.
- Confirm each sensitive entry.
- Return a synthesized spoken response.

If the call requires an action that the service cannot reliably detect, the secretary should tell the user rather than silently proceeding.

### S7 — Secretary response

The watch receives a response as text and/or synthesized speech. Commands available during playback:

- Repeat.
- Slower.
- Stop.
- Summarize.
- Continue.
- Cancel.

The device should avoid maintaining an open microphone during speech playback unless needed for an interruption command.

### S8 — Location request

The user can ask for:

- GPS state.
- Current position, if GNSS is enabled and a fix is available.
- Approximate network area, if authorized carrier information is available.
- Directions.
- Whether location is currently being shared.

The response must distinguish exact coordinates, estimated position, serving-cell information, and unavailable data.

### S9 — Emergency initiation

Emergency initiation should have a dedicated safety design and must be tested against accidental activation and false recognition. The watch should provide immediate feedback that emergency mode has started, is preparing, is connected, failed, or remains uncertain.

The emergency pathway must not depend solely on ordinary AI text service availability. It requires a real supported voice-call and emergency-location implementation.

### S10 — Emergency call

The device uses the certified emergency voice pathway. The system should attempt to provide the best available location through the approved mechanism. The watch must not claim that GPS is available when the hardware switch has disabled it.

### S11 — Error / recovery

Errors include:

- Speech not understood.
- Low battery.
- No cellular service.
- Data service unavailable.
- Telephony provider failure.
- DTMF unsupported.
- Location unavailable.
- Emergency call failure or uncertainty.

Each error should have a short spoken explanation and a simple recovery option. Critical failures should not be hidden behind generic language such as "something went wrong."

## General interaction rules

1. Confirm before committing sensitive or irreversible actions.
2. Prefer short prompts and short responses.
3. Never silently guess a digit, contact, extension, or emergency action.
4. Provide spoken feedback for every tactile action.
5. Allow repeat, back, cancel, and help from every non-emergency state.
6. Make emergency activation fast but separately testable.
7. Make privacy state visible, audible, and accurately described.
8. Design for noisy environments, speech differences, disability access, and limited technical literacy.
