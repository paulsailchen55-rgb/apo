# Open-Source Audio Processing and Android Microphone Control Research

Author: Paul Statchen
Date: 2026-09-18
Status: Research inventory; components and licenses require project-specific verification before integration.

## Purpose

The Simple Voice Link project needs a reliable voice path in which the intended speaker remains understandable while background speech, room noise, echo, handling noise, and other unwanted audio are reduced.

The preferred strategy is to reuse mature open-source components rather than implement the signal-processing algorithms from scratch. The project should first inventory existing libraries, Android integrations, licenses, performance, hardware requirements, and limitations.

This is not a claim that any one library solves the problem. The target is a layered audio pipeline.

## Audio-processing layers to investigate

1. Microphone hardware and microphone array
   - Number and placement of microphones
   - Directionality and physical acoustic design
   - Signal-to-noise ratio
   - Frequency response
   - Wind and handling noise
   - Hardware voice-processing features supplied by the phone manufacturer

2. Beamforming
   - Use multiple microphones to emphasize sound arriving from the intended direction
   - Investigate whether the Android device exposes the required microphone channels and metadata
   - Do not assume a normal Android app can control the manufacturer's beamforming implementation

3. Acoustic echo cancellation (AEC)
   - Uses the speaker/playback signal as a reference to reduce speaker-to-microphone echo
   - Important for speakerphone use
   - WebRTC Audio Processing and SpeexDSP are major open-source candidates

4. Noise suppression / speech enhancement
   - RNNoise is a BSD-3-Clause recurrent-neural-network noise suppression library
   - WebRTC Audio Processing includes real-time voice-processing components
   - SpeexDSP includes noise suppression and related preprocessing
   - Android-specific projects using neural voice-isolation models should be evaluated separately

5. Automatic gain control (AGC)
   - Keeps speech within a useful level range
   - Must be tested carefully because aggressive gain can raise background speech/noise

6. Dynamic compression / limiting
   - Prevents excessive peaks and can improve intelligibility
   - Investigate existing DSP components rather than assuming a generic compressor is sufficient

7. Voice activity detection (VAD)
   - Determines whether speech is present
   - Useful for gating, transmission decisions, and testing
   - VAD should not be treated as equivalent to voice isolation

8. AI voice isolation
   - Investigate on-device models such as GTCRN and related speech-enhancement models
   - Determine whether they suppress competing human speech, not merely stationary noise
   - Measure latency, CPU/NPU/GPU load, battery consumption, artifacts, and intelligibility

## Candidate open-source components found for investigation

### RNNoise

Repository: https://github.com/xiph/rnnoise

RNNoise is a recurrent-neural-network noise-suppression library. The repository identifies its license as BSD-3-Clause. It is a strong candidate for an initial local noise-suppression experiment, but noise suppression is not the same thing as reliably separating one speaker from another.

### SpeexDSP

Repository: https://github.com/xiph/speexdsp

SpeexDSP provides acoustic echo cancellation and preprocessing functions including noise suppression, residual echo suppression, automatic gain control, and voice activity detection. Its source contains a permissive BSD-style license.

This makes it a useful candidate for a conventional DSP pipeline and a comparison baseline against newer neural approaches.

### WebRTC Audio Processing

WebRTC's Audio Processing Module contains real-time communications components including echo cancellation, gain control, noise suppression, high-pass filtering, and voice detection. The WebRTC source is BSD-licensed, with additional patent/IP notices that must be reviewed before redistribution.

A current implementation or maintained binding should be preferred over copying an old WebRTC snapshot.

### webrtc-audio-processing Rust bindings

Repository: https://github.com/tonarino/webrtc-audio-processing

This project provides Rust bindings for the webrtc-audio-processing library and identifies a BSD-3-Clause license. It is worth evaluating if the phone software eventually uses Rust, but the underlying native WebRTC processing and Android build path still need to be understood.

### Android real-time voice-isolation projects

Repository: https://github.com/sk2andy/android-realtime-voice-isolation

This project demonstrates on-device Android voice isolation using GTCRN, ONNX Runtime, and Shizuku. Its repository states that its own source is MIT-licensed and that the GTCRN model comes from an MIT-licensed upstream project; third-party licenses remain separate.

It is especially relevant because it demonstrates that Android-specific on-device voice isolation can be implemented without sending the audio to a cloud service. Its architecture and compatibility constraints need independent testing before adoption.

Repository: https://github.com/chabandou/poise-android

Poise Android describes itself as a real-time, system-wide Android speech-isolation application using machine-learning denoising. Its licensing and third-party dependencies must be checked before any reuse. The repository is useful as an architectural reference even if its code is not reused.

## Important distinction: noise cancellation versus competing-speaker isolation

The project requirement is stronger than ordinary noise cancellation.

Example:

Person A is speaking into the phone while Person B is talking nearby.

A conventional noise suppressor may reduce some of Person B's voice, but speech is a structured signal and may not be treated as ordinary background noise. The project therefore needs tests specifically involving competing human speech.

The acceptance test should include:
- one intended speaker
- one nearby competing speaker
- multiple competing speakers
- television/radio
- music
- street/traffic noise
- wind
- handling noise
- reverberant rooms
- speakerphone echo
- simultaneous intended speech and background speech

The receiving end should be used for evaluation, because the objective is what the other person actually hears.

## Processing location

Three broad architectures should be compared.

### Phone-local processing

Microphone -> Android audio capture -> local DSP/ML -> telephone/VoIP transmission.

Advantages:
- audio can be processed before leaving the device
- lower dependence on network latency
- potentially usable with ordinary cellular or local communication paths

Questions:
- Can Android expose the necessary audio path?
- Can the application keep control of its input?
- Does the phone manufacturer insert additional processing?
- Can competing applications or system services access the microphone?
- What happens during a conventional cellular call?

### Calling-service processing

Microphone -> phone/cellular/VoIP -> service -> voice processing -> recipient.

Advantages:
- processing can use a larger CPU/GPU
- service can be updated centrally

Disadvantages:
- raw or partially processed speech may leave the phone
- network latency and availability
- privacy and data-retention questions
- service-specific licensing and terms

### External audio processor

Microphone hardware -> dedicated DSP/USB/audio interface -> phone.

This may be useful if Android's internal routing prevents the desired isolation architecture. An external processor can create a controlled audio boundary, but introduces hardware, power, compatibility, and cost considerations.

## Android microphone control problem

The desired security model is stronger than simply giving the application RECORD_AUDIO permission.

The goal is approximately:

Microphone -> designated application/audio pipeline -> communication service

with no unnecessary competing application touching the microphone.

Android does not generally provide an ordinary application with absolute ownership of the microphone. Android manages audio input sharing and privacy-sensitive sources at the operating-system level.

Current Android documentation states that multiple applications can interact with audio input under defined sharing rules, while voice calls receive special treatment. Android also exposes microphone privacy indicators and permission controls.

For a dedicated device, investigate:
- Device Owner / managed-device mode
- kiosk / lock-task mode
- default dialer / Telecom APIs
- foreground microphone service
- application permissions
- audio focus
- microphone privacy controls
- disabling or removing unnecessary applications
- OEM-specific audio routing
- whether the device can be configured without Google Play Services
- whether the chosen Android build permits stronger system-level control
- whether a custom Android build is necessary

A kiosk launcher alone should not be treated as equivalent to exclusive microphone control.

## Google Play Services and system components

The requirement "nothing else touches the microphone" needs to be translated into a technically testable statement.

Possible test questions:
- Which packages have RECORD_AUDIO?
- Which packages actually open an audio input device?
- Can microphone access be observed during normal operation?
- Does the device permit revoking microphone permissions from all nonessential packages?
- Which system/privileged services retain access?
- Does the cellular telephony stack use the microphone independently of the app?
- Does the manufacturer DSP process microphone data below the Android application layer?
- Can the phone operate without Google Play Services?
- If Play Services remains installed, can its microphone permission be disabled without breaking required functions?
- Can the communication app remain the only ordinary application with microphone permission?

The phrase "exclusive microphone ownership" should remain a design goal until the exact Android/OEM architecture proves what level of isolation is actually possible.

## License and integration screening

"Free" should not be treated as equivalent to "no legal obligations."

For every candidate component record:
- source repository
- exact version/commit
- SPDX license identifier
- license text
- copyright notices
- patent notices or additional IP grants
- model license, separately from source-code license
- training-data restrictions, if applicable
- third-party dependencies and their licenses
- Android compatibility
- redistribution requirements
- whether modifications must be disclosed
- whether binary redistribution is permitted
- whether commercial use is permitted
- whether the repository actually contains the model weights used by the application

The project should prefer permissive licenses such as BSD-2-Clause, BSD-3-Clause, MIT, or Apache-2.0 when technically suitable, while still performing a complete dependency review.

No candidate should be described as "no liability" merely because it is open source. Open-source licenses contain their own disclaimers and obligations, and the final deployment creates separate product, communications, privacy, accessibility, and possibly telecommunications responsibilities.

## Initial integration strategy

Do not build a new voice-isolation algorithm first.

Instead:

1. Select one Android phone model with a known microphone configuration.
2. Build a minimal test application with controlled audio capture.
3. Establish a raw-audio baseline.
4. Test Android's built-in voice communication processing.
5. Test WebRTC Audio Processing.
6. Test SpeexDSP.
7. Test RNNoise.
8. Test one current on-device speech-isolation model.
9. Test combinations only after each component is measured independently.
10. Compare processing on the phone against processing after transmission.
11. Record CPU, latency, battery, intelligibility, artifacts, and competing-speech suppression.
12. Determine the strongest microphone-routing boundary actually achievable on the selected Android build.

## Core requirement

The endpoint should be simple for the person using it.

The complexity should be moved into the system behind the button, while preserving a reliable, inspectable, maintainable audio path.

The desired result is not "make the microphone quiet."

The desired result is:

A designated person can speak naturally into a simple device, and the remote listener receives that person's speech clearly even when the surrounding environment contains other speech and ordinary noise.

## Evidence status

Established from current project/repository documentation:
- RNNoise is an open-source RNN noise-suppression library with a BSD-3-Clause license.
- SpeexDSP contains AEC, noise suppression, AGC, and VAD components under a permissive BSD-style license.
- WebRTC Audio Processing contains AEC, gain control, noise suppression, and voice-detection components under BSD licensing with additional IP/patent notices.
- Android has operating-system rules governing microphone access, audio-input sharing, foreground microphone services, and voice calls.
- Current Android open-source projects demonstrate on-device voice-isolation approaches.

Still requiring testing or verification:
- whether any candidate reliably suppresses nearby human speech in the intended use case
- whether a particular phone's microphone hardware is suitable
- whether Android permits the required degree of application-level microphone isolation
- whether Google Play Services can be removed or disabled without unacceptable consequences
- whether a custom ROM/build is necessary
- exact licenses of every dependency/model in the final build
- performance and battery impact on the selected phone
- cellular-call integration and whether processing can be inserted into the actual call uplink

Guiding principle: reuse mature open-source components where possible, but test the complete hardware-to-remote-listener chain rather than assuming that a library's advertised function equals the project's required result.
