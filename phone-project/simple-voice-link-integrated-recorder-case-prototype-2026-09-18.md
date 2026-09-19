# Simple Voice Link — Integrated Recorder Case Prototype

**Date:** 2026-09-18  
**Status:** Experimental hardware branch. The architecture below is a prototype hypothesis, not a validated device design.

## Purpose

This document records a specific physical prototype direction within Simple Voice Link: take a small, inexpensive digital voice recorder or similar audio-processing device, integrate it into a phone case, and use it as an external microphone-processing stage for an ordinary cellular telephone.

The important distinction is that the recorder is being considered first as an experimental processing engine, not as the final product. If it proves that useful real-time speech processing can be performed in a small, inexpensive package, the same measured requirements could later be implemented with a dedicated DSP, microcontroller, or other purpose-built audio circuit.

## Concept

The proposed physical chain is:

```
User's voice
    ↓
Case-mounted microphone near the mouth
    ↓
Small digital recorder / audio processor
    ↓
Real-time microphone processing
    ↓
Processed audio output
    ↓
Level / bias interface
    ↓
Phone headset-microphone input
    ↓
Normal cellular call
    ↓
Remote listener
```

The recorder would have its own power source rather than depending entirely on the phone. In a later integrated version, the recorder electronics could be mounted inside or onto the back of a phone case, with its microphone, controls, battery, and audio interface arranged as one accessory.

A future sealed version is conceivable, but sealing should come only after the electronics, charging, heat, battery, audio routing, and serviceability have been tested in an open or temporary enclosure.

## Primary hypothesis

A small consumer recorder may be repurposed as a compact microphone preamp, ADC/DSP/noise-processing stage, and output stage for the phone's ordinary cellular microphone path.

The critical question is not whether a recorder can save a noise-reduced recording. The critical question is whether its **live output while recording** contains the processed microphone signal.

A recorder may perform noise reduction or filtering on material written to storage while routing a lower-latency or substantially unprocessed signal to its headphone/line output. This must therefore be tested for each candidate recorder rather than assumed from the presence of a feature named "noise reduction," "noise cut," or similar.

## Why this is interesting for Simple Voice Link

The larger project has identified competing human speech as a particularly difficult audio problem. The desired microphone system should improve the signal heard by the person at the remote end of an ordinary telephone call, not merely make a local recording sound cleaner.

This prototype creates a simple physical experiment:

- Put the microphone close to the intended speaker.
- Give the microphone a dedicated processing stage.
- Send the processed result into the phone's ordinary cellular microphone path.
- Leave the telephone network itself unchanged.
- Evaluate what the remote listener actually hears.

This separates the microphone/audio-processing problem from the more complicated questions of AI telephone intermediaries, VoIP, and application-level audio processing.

## Physical architecture

The case would contain or support several distinct elements:

1. A microphone positioned close enough to the intended speaker to improve the desired-speech-to-background ratio.
2. A small recorder or audio-processing board.
3. An independent power source for the external electronics.
4. An output interface compatible with the phone's headset microphone input.
5. The phone's normal earpiece or speaker for incoming call audio.
6. Physical separation between the microphone and the phone's downlink speaker/earpiece.
7. Access to charging and service points as required during prototyping.

The microphone should not simply be placed wherever there is empty space inside the case. Its location relative to the user's mouth, the phone's earpiece, the case openings, and competing sound sources is part of the experiment.

## Target handset

The first physical target can be the Moto G Power already available for the project.

The exact Moto G Power model should be recorded before a final enclosure is designed. Different generations and variants may differ in dimensions, connectors, microphone locations, headset behavior, charging hardware, and other details.

The first prototype therefore should use a temporary or easily modified case rather than committing immediately to a permanently sealed enclosure.

## Acoustic architecture

The external microphone and phone speaker create a duplex audio problem.

If the incoming caller's voice from the phone's speaker is acoustically coupled back into the external microphone, the caller may hear their own voice returned through the uplink. The case should therefore preserve a handset-like separation:

```
          PHONE TOP
      [earpiece / speaker]
             ↓
       incoming audio

      physical separation

       [microphone]
             ↑
       user's voice
          PHONE BOTTOM
```

A close microphone can improve rejection of distant speech and other background sounds, but passive proximity is not the same thing as active noise cancellation. The prototype should measure both the acoustic benefit of microphone placement and the additional benefit, if any, from digital processing.

## The critical recorder experiment

Before taking a recorder apart, determine exactly what appears at its live output.

The test should compare at least:

- raw microphone signal, where accessible;
- recorded/saved output after the recorder's processing;
- live headphone/line output while recording;
- live output with processing features enabled;
- live output with those features disabled.

The most useful experiment is to feed the recorder a controlled mixture of intended speech plus a competing voice or other background sound and then examine the signal coming from the live output.

The question is:

> Does the live output contain the processed signal that we want to feed to the telephone?

If yes, the recorder becomes a candidate for the case prototype.

If no, the recorder may still be useful for recording experiments, but it should not be treated as the live-processing engine.

## Level and bias interface

A recorder's headphone or line output should not be assumed to be electrically compatible with a phone's microphone input.

The interface may require attenuation, AC/DC coupling appropriate to the circuits involved, and a microphone-line load or other arrangement required by the target phone's headset detection.

The prototype should therefore use a purpose-designed interface between the recorder output and the phone input rather than connecting an unknown headphone output directly to the handset microphone line.

The exact electrical interface should be measured and documented for the target handset and recorder combination.

## TRRS/headset path

The earlier research identified conventional CTIA-style four-pole headset connections as the likely starting point for a wired microphone path:

```
Left — Right — Ground — Microphone
```

However, the project should treat the exact behavior of the target Moto G Power as a test result, not as a universal Android guarantee.

The initial experiment should use a known-compatible wired headset and establish:

1. that the phone recognizes the external microphone;
2. that an ordinary carrier call uses it;
3. what the remote listener hears;
4. what happens when the external microphone connection is interrupted;
5. whether the phone returns to its internal microphone;
6. whether the call remains connected.

The desired fallback behavior is useful, but it must be demonstrated on the actual supported handset.

## Independent power

The recorder/audio processor should initially have its own battery or other independently managed power source.

During bench testing, the electronics should remain accessible. Only after the system has demonstrated stable operation should the project consider integrating the battery and charging system into the case.

A permanently sealed lithium-ion battery arrangement should not be treated as a finished design. Battery protection, charging control, thermal behavior, mechanical protection, and serviceability all need separate verification.

A prototype enclosure should preferably remain openable rather than permanently glued shut.

## Integrated case concept

If the live-processing experiment succeeds, the next physical version could look approximately like:

```
┌─────────────────────────────────────┐
│             PHONE CASE              │
│                                     │
│   phone                             │
│   ┌─────────────────────────────┐   │
│   │                             │   │
│   │        Moto G Power         │   │
│   │                             │   │
│   └─────────────────────────────┘   │
│                                     │
│  [mic]   [recorder/DSP] [battery]  │
│            │                        │
│            └── processed audio ──┐  │
│                                  │  │
│                         TRRS interface│
└─────────────────────────────────────┘
```

This is only a conceptual layout. The actual positions should be determined by the phone's microphone, speaker, connector, battery, and case geometry.

The recorder does not necessarily need to occupy the entire rear surface. Once the signal path is understood, its electronics can be separated from the microphone and speaker and arranged for the smallest practical package.

## Staged experimental order

### Phase 1 — Prove the phone path

Use a standard, known-compatible wired headset.

Establish a baseline call and verify the external microphone path. Test the desired fallback behavior by interrupting the microphone connection.

Do not modify the phone case yet.

### Phase 2 — Prove the passive microphone arrangement

Build a temporary case or bracket with a close microphone and a separated earpiece/speaker.

Do not add digital processing.

Test whether microphone placement alone materially improves the remote listener's ability to understand the intended speaker when other people are talking.

### Phase 3 — Test the commercial recorder as a live processor

Connect the case-mounted microphone to a candidate recorder.

Determine whether the recorder's live output actually contains the desired real-time processing.

Test the recorder outside the phone case first. This avoids wasting time modifying the enclosure around hardware that may not perform the required function.

### Phase 4 — Connect the processed output to the phone

Use the appropriate level/bias interface to feed the recorder's processed output into the phone's microphone input.

Test a real cellular call.

Evaluate the signal at the remote end, not merely with local headphones.

### Phase 5 — Integrate the hardware

Only after the preceding phases work should the recorder be opened or its electronics removed from their original enclosure.

Mount the electronics, microphone, battery, and interface into a temporary phone-case assembly.

Test heat, electrical stability, mechanical strain, audio feedback, charging, and failure behavior.

### Phase 6 — Investigate purpose-built processing

If the recorder proves the concept but is too large, expensive, power-hungry, or otherwise unsuitable for a permanent case, replace it with a smaller dedicated processing module.

The measured requirements from the recorder experiment should guide that redesign.

Possible directions include:

- low-power microcontroller/DSP;
- dedicated audio-processing IC;
- embedded Linux board;
- purpose-built audio front end;
- another compact wired audio processor.

The recorder experiment therefore becomes a requirements-discovery tool for the eventual hardware.

## Candidate hardware

The repository may retain several candidate paths rather than selecting one prematurely.

A small commercial handheld recorder is useful because it is a relatively complete, accessible audio system. Candidate models should be evaluated specifically for their live monitoring/output behavior.

Small recorder breakout boards may be useful when a permanent embedded prototype becomes appropriate.

A microcontroller or embedded Linux board becomes more attractive if the project needs custom real-time noise suppression or speech isolation.

Bluetooth can remain a separate experimental branch, but it should not replace the wired path in the first prototype. Wireless audio introduces additional latency, pairing, power, compatibility, and failure questions.

## What the prototype must demonstrate

A successful prototype should demonstrate the complete chain:

```
intended speaker
    ↓
close microphone
    ↓
real-time processing
    ↓
compatible electrical interface
    ↓
Moto microphone input
    ↓
ordinary cellular call
    ↓
remote listener
```

The meaningful result is not merely that every component produces sound.

The meaningful result is that the remote listener receives intelligible speech with measurable improvement under the difficult conditions the project cares about, particularly competing human speech.

## Test conditions

At minimum, compare:

- intended speaker alone;
- intended speaker plus one competing speaker;
- multiple competing speakers;
- television or radio;
- music;
- ordinary room noise;
- traffic/street noise where relevant;
- reverberant rooms;
- handling noise;
- different microphone positions;
- different speaking distances;
- incoming caller speech through the phone speaker;
- simultaneous incoming and outgoing speech.

The project should record both the local input conditions and what the remote listener actually hears.

## Failure modes to document

Potential failures include:

- recorder processes saved recordings but not live output;
- recorder introduces too much latency;
- recorder output level is incompatible with the phone input;
- headset detection fails;
- external microphone is not selected by the phone;
- microphone fallback does not behave as expected;
- acoustic feedback occurs;
- processing damages speech intelligibility;
- competing speech is not sufficiently suppressed;
- battery introduces noise into the audio path;
- electronics overheat inside the case;
- charging interferes with audio;
- case geometry blocks phone microphones or speakers;
- the integrated device becomes difficult to service;
- the external electronics fail while the phone remains operational;
- the accessory causes an unexpected loss of ordinary telephone functionality.

Each failure is useful information because the purpose of this branch is to discover the requirements of a workable device.

## Relationship to the broader Simple Voice Link architecture

This branch is intentionally below the AI-secretary and network layers.

The architecture can be viewed as:

```
[Person]
    ↓
[Microphone / physical audio interface]
    ↓
[External processing accessory]
    ↓
[Ordinary phone microphone input]
    ↓
[Cellular telephone system]
    ↓
[Remote person or future communication intermediary]
```

The accessory therefore does not require an AI secretary, VoIP service, or custom cellular infrastructure.

That makes it a useful independent experiment within the larger project.

If the accessory works, it can serve as the audio front end for several future architectures.

## Relationship to the existing research

The larger Simple Voice Link work identified several possible ways to improve speech quality, including microphone proximity, beamforming, acoustic echo cancellation, noise suppression, voice isolation, and other signal-processing methods.

This prototype does not assume which algorithm will ultimately be best.

Its immediate purpose is to establish a physical signal path in which some real-time processing can occur before the signal reaches an ordinary cellular call.

Once that path exists, different processing methods can be compared without changing the basic telephone architecture.

## Open questions

1. Which inexpensive recorder actually exposes its processed microphone signal on its live output?
2. What processing features remain active during live monitoring?
3. What latency does the processing introduce?
4. What output level and impedance does the recorder provide?
5. What exact microphone-line interface does the target Moto G Power require?
6. Can the phone reliably use the external processed microphone during a carrier call?
7. What happens when the accessory loses power?
8. Can the phone return to its internal microphone without ending the call?
9. How much improvement comes from microphone proximity alone?
10. How much additional improvement comes from digital processing?
11. Which processing algorithms work best against competing human speech?
12. How much battery capacity is required for an ordinary day's use?
13. How much heat is generated inside a sealed case?
14. Can the electronics be made serviceable after integration?
15. Can the entire accessory eventually be reduced to a purpose-built board substantially smaller than the commercial recorder?

## Development principle

The project should not begin by designing the final sealed phone case.

It should begin by proving the audio path with inexpensive, replaceable hardware.

The sequence is:

```
prove the phone interface
        ↓
prove microphone placement
        ↓
prove live recorder processing
        ↓
prove processed audio into cellular call
        ↓
measure the benefit
        ↓
integrate the hardware
        ↓
miniaturize only if justified
```

This keeps the physical prototype inexpensive and makes every later design decision depend on measured behavior rather than assumptions.

## Status and evidence boundary

This document records a project hypothesis and experimental plan derived from the Simple Voice Link work.

It does not establish that any particular recorder provides the required real-time processed monitoring output. It does not establish that a particular Moto G Power variant will behave exactly as described. It does not establish that a particular battery, microphone, recorder, or enclosure is safe for a permanently sealed consumer device.

Those questions are experimental and should be verified before the design is treated as a working device.

The commercial recorder is therefore a **candidate experimental component**, not a selected final component.
