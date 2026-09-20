# Design Parameters and Decision Record

## Status key

- **Chosen direction:** currently preferred by the conversation.
- **Candidate:** plausible option requiring testing or research.
- **Rejected/deprioritized:** considered but not preferred at this stage.
- **Unresolved:** intentionally left open.

## Human interface

| Topic | Current direction | Status | Rationale |
|---|---|---|---|
| Display | Ordinary watch appearance; time and possibly date only | Chosen direction | Keep the device simple and socially familiar |
| Touchscreen | Avoid as the primary interface | Chosen direction | Reduce complexity, power use, and interaction burden |
| Physical keypad | Avoid as the primary interface | Chosen direction | Secretary handles numeric entry where possible |
| Voice interface | Primary interaction method | Chosen direction | User speaks naturally instead of navigating menus |
| Rotary bezel | Optional tactile fallback | Candidate | Could support digits or menu choices without a full keypad |
| Twelve positions | Inspired by clock/watch geometry | Unresolved | Need test whether twelve positions are efficient for ten digits and repeated entry |
| Confirmation | Required for consequential numeric actions | Chosen direction | Prevent misrecognition and accidental submission |

## Telephony

| Topic | Current direction | Status | Rationale |
|---|---|---|---|
| Normal communication | Text/data-first with synthesized speech | Chosen direction | Reduce continuous audio streaming and battery use |
| Ordinary voice calls | Not the normal communication method | Chosen direction | Secretary provides voice-like interaction without conventional calls |
| 911 | Genuine cellular voice capability | Chosen direction | Emergency service requirements cannot be replaced by an assumed AI text path |
| DTMF | Secretary generates keypad tones | Candidate | Needed for IVR menus, extensions, and numeric systems |
| Account numbers | Spoken input, read-back, confirmation, then DTMF or supported entry | Candidate | Avoid physical keypad while reducing errors |
| IVR navigation | Secretary detects prompts or receives user instructions | Candidate | Requires reliable call-audio and signaling control |
| Unsupported systems | Fallback to human assistance or user-directed action | Unresolved | Some systems may not expose usable prompts or keypad control |

## Processing and power

| Topic | Current direction | Status | Rationale |
|---|---|---|---|
| Wake-word | Low-power local detection if feasible | Candidate | Avoid transmitting continuously and preserve battery |
| Simple commands | Local recognition where reliable | Candidate | Digits and commands may be handled with a small model |
| General speech | Remote or hybrid processing | Candidate | Complex recognition and AI reasoning are power-intensive locally |
| AI reasoning | Remote secretary service | Chosen direction | Watch should remain simple and lightweight |
| Speech synthesis | Remote or carefully optimized local output | Candidate | Need compare latency, quality, bandwidth, and battery cost |
| Continuous audio stream | Avoid in normal mode | Chosen direction | Intended to improve efficiency and network scalability |
| Battery goal | All-day operation | Chosen direction | Primary engineering objective, not yet a measured specification |

## Location and privacy

| Topic | Current direction | Status | Rationale |
|---|---|---|---|
| GNSS/GPS | Physically controllable | Chosen direction | User should have a verifiable hardware state |
| Location indicator | Mechanical position plus light, sound, or vibration | Candidate | Make state observable rather than merely software-reported |
| Cellular visibility | Disclose that GPS off does not disable carrier visibility | Chosen direction | Avoid misleading privacy claims |
| Carrier tower location | Explore authorized carrier/network API | Candidate | Tower data may be available to the carrier but not automatically to the secretary |
| Navigation | Location enabled with explicit user control | Chosen direction | Directions require current location and user awareness |
| Emergency location | Separate emergency policy | Unresolved | Need define behavior when ordinary GPS is disabled |
| Hardware verification | Report actual GNSS power/path state | Candidate | Software should not be able to falsely represent switch position |

## Emergency reliability

- Emergency calling must not depend exclusively on the AI backend.
- The system needs fallback behavior for no data, no speech recognition, no GPS, weak coverage, low battery, and backend outage.
- Emergency activation must address false positives and accidental activation.
- 911 compatibility requires carrier, modem, location, regulatory, and certification research.
- Any emergency override of privacy settings must be explicit, documented, and visible.

## Security and privacy

- Sensitive numbers should be minimized in logs and encrypted in transit and at rest.
- Read-back confirmation should be used before transmitting account or benefits numbers.
- The system should distinguish a user's request from an automated prompt's request.
- Voice synthesis resembling another person requires consent, authorization, and anti-impersonation controls; it is not an assumed default feature.
- The user should be told when the secretary is acting as an intermediary rather than directly connecting an ordinary call.

## Decision discipline

No design item is locked merely because it appears in this document. A locked decision should include:

1. The problem being solved.
2. Alternatives considered.
3. The reason for selection.
4. Battery, usability, privacy, and reliability consequences.
5. A test or validation plan.
6. Conditions under which the decision can be reopened.
