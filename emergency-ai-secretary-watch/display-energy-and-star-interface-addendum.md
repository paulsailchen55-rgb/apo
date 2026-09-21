# Display, Energy, and Single-Star Interface Addendum

**Status:** Exploratory design note
**Relationship:** Extends `design-notes.md`; does not replace prior decisions.

## 1. New design direction

The watch remains voice-first. The display is not intended to become a miniature smartphone or a text-heavy interface. Its primary purpose is to communicate state visually and provide limited manual input when speech is unavailable, unsuitable, or unsuccessful.

Preferred display research direction:

- Reflective or transflective LCD, with actual low-power parts compared by datasheet.
- Consider memory-in-pixel or other static-image-preserving architectures.
- Evaluate readability, glare, contrast, refresh behavior, touch compatibility, and power use together.
- Do not assume that reflective LCD is automatically more comfortable or more efficient than every e-ink or LCD alternative.

## 2. Integrated solar collection

Explore photovoltaic energy harvesting integrated into, behind, around, or optically coupled with the display assembly. Quantum-dot photovoltaics may be investigated as one possible technology, but they are not a fixed requirement.

The optical and electrical design must account for potential tradeoffs among:

- Display visibility and reflected light.
- Solar collection area and efficiency.
- Touch-sensor operation.
- Display refresh and animation.
- Battery charging and power-management losses.

Solar collection should initially be treated as supplemental energy harvesting until measured performance demonstrates otherwise.

## 3. Single-star voice visualization

The preferred visual identity is one individual star rather than a complex constellation or continuous full-screen FFT visualizer.

Suggested states:

- **Idle:** Static star or very low-activity presentation.
- **Listening:** Gentle pulse to indicate microphone/listening state.
- **Processing:** Subtle movement or brightness change without unnecessary continuous animation.
- **Speaking:** A restrained dance or pulse related to broad speech characteristics, such as amplitude, rhythm, or speech activity.
- **Emergency interaction:** The star may remain visible while essential controls appear.

The star is an expressive status indicator, not a requirement to reproduce every frequency component of the audio. A low-cost implementation may use speech activity, amplitude envelopes, and limited spectral features instead of a continuously running particle system.

## 4. Touch interface

Touch should be contextual and appear only when needed. The preferred interface contains no persistent text-heavy navigation.

Potential manual functions include:

- Numeric entry when the user cannot speak or speech recognition fails.
- Confirm, cancel, repeat, and correction controls.
- Emergency-related controls that are clearly distinguished from ordinary interaction.

A capacitive touchscreen overlay is one candidate. It must be evaluated for operation with wet fingers, gloves, limited dexterity, accidental touches, low visibility, and accessibility. The prior tactile bezel concept remains a separate fallback option and is not superseded by this note.

## 5. Thirty-day power objective

The long-term goal is one charge supporting approximately 30 days of operation. This target must be expressed through separate operating profiles rather than a single vague runtime claim.

At minimum, test:

1. Deep idle / standby.
2. Voice-ready state during waking hours.
3. Intermittent active conversations.
4. Continuous or near-continuous audio transmission as a stress case.
5. Emergency operation.

The distinction between being available to speak and actively transmitting audio for 12–16 hours per day is critical. Cellular modem activity, signal strength, microphone and speaker use, processor workload, remote speech services, and display activity may dominate energy consumption. The star animation and display must therefore be event-driven and power-limited, but display selection alone cannot establish 30-day feasibility.

## 6. Preliminary power-first position

For early prototyping, prefer:

- Static or nearly static star in idle.
- Event-driven animation only during listening, processing, or speaking.
- Low-refresh animation and limited visual complexity.
- Local low-power wake detection where practical.
- Compact command/text-first data exchange when compatible with the required service.
- Explicit measurement of modem active time and actual voice-transmission duration.
- Solar harvesting as supplemental power unless validated by testing.

## 7. Open research questions

- Which reflective/transflective LCD parts support the required touch and animation behavior at acceptable power?
- Can a photovoltaic layer be integrated without unacceptable loss of display visibility or touch performance?
- What is the lowest useful refresh rate for a recognizable single-star voice indicator?
- How much energy does the star visualization consume compared with the cellular modem and audio path?
- What battery capacity and physical size are required for 30 days under defined communication profiles?
- Can the screen remain mostly static while the device still communicates clear listening, processing, speaking, and emergency states?

This addendum records a design direction for further discussion and testing. It is not a validated hardware specification.
