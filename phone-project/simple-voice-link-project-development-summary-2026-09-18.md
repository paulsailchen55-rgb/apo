# Simple Voice Link — Project Development Summary

**Date:** 2026-09-18  
**Status:** Project development summary based on the working conversation; exploratory and not a validated deployment specification.

## Why this summary is preserved

The working conversation expanded Simple Voice Link from a single-phone idea into a broader community-accessible communication technology project. The goal is not to prescribe one device or one implementation. The project should explore multiple technical paths and let the available equipment, user's needs, environment, and reliability requirements determine the appropriate path.

## Core direction

The project is intended to make voice communication substantially simpler for people who have difficulty using an ordinary smartphone, while preserving a dependable telephone path and avoiding unnecessary dependence on data services.

The original concept centers on a very simple phone: its own number, a very small interface, and a designated contact. The phone should be able to remain useful as a normal cellular telephone even when other connectivity is disabled.

The broader project asks whether the same accessibility goal can be achieved through one or more of the following:

- Reconfigure an existing Android phone.
- Build a simple launcher or dedicated communication application.
- Use Android managed-device / kiosk controls where appropriate.
- Use a phone's existing accessibility and voice-processing capabilities.
- Add an external wired audio-processing device.
- Develop a phone-case or headset-style microphone/audio-processing accessory.
- Build an application-based VoIP version where data connectivity is appropriate.
- Develop a purpose-built handset if the other approaches prove insufficient.
- Provide supplier-facing hardware requirements when custom manufacturing becomes appropriate.

The project should therefore be understood as an options architecture rather than as a single product specification.

## Cellular voice and data/VoIP are separate project tracks

The research work identified an important distinction between ordinary cellular voice calling and application-based VoIP.

For the standard cellular path, the phone's telephony system and carrier network control the call audio path. An ordinary application cannot simply insert its own noise-processing algorithm into that cellular call stream. This means the project's voice-quality improvements for a cellular-only phone may need to occur at the microphone/audio boundary rather than inside the cellular call software.

For a VoIP implementation, the calling application owns the audio path and can therefore incorporate software-based noise suppression or speech-isolation processing. That creates additional requirements for data/Wi-Fi, service providers, privacy, reliability, and emergency calling.

The project therefore keeps the cellular telephone path as the standard/safety path and treats VoIP as an additional track rather than automatically replacing cellular calling.

## The external audio-processing idea

The conversation developed the idea of a wired audio device connected through the phone's headset/microphone connection.

The purpose would be to process the user's microphone signal before it reaches the phone's normal cellular call path. The same general architecture could potentially process incoming audio before it reaches the user's ear, creating a two-way "smart headset" or audio front end.

The preferred connection discussed was the wired microphone/headset jack rather than Bluetooth. USB-C remains a possible research path but introduces compatibility and charging-port considerations.

The hardware should be designed so that failure does not silently create an unsafe communication condition. One proposed behavior is a fail-open arrangement in which a failed or unpowered accessory allows the phone to revert to its ordinary telephone behavior. This behavior must be tested on each supported phone rather than assumed.

A critical practical question is microphone placement. A microphone close to the intended speaker may improve the signal-to-background ratio before sophisticated processing is even applied. A case-mounted microphone may be too far from the user's mouth. A boom, clip, or chin-height microphone may therefore outperform a more complicated distant microphone system in some environments.

## The real audio problem

The project is not merely trying to cancel generic background noise.

The difficult use case is an intended speaker talking while other people are talking nearby. The system therefore needs to distinguish the desired speaker from competing human speech as well as from ordinary noise such as television, music, beeps, traffic, wind, handling noise, and reverberation.

The receiving end should be used for evaluation, because the relevant result is what the other person actually hears.

Candidate open-source processing components identified during the work include RNNoise, SpeexDSP, WebRTC Audio Processing, DeepFilterNet, and newer speech-isolation projects. Their individual licenses, dependencies, model terms, performance, and suitability still require project-specific verification.

The preferred development strategy is to reuse mature components and measure them before attempting to create a new algorithm.

## Phone configuration and microphone control

The desired phone should expose as little unnecessary complexity as possible to the person using it.

The project should investigate several levels of control, from simple screen pinning and launcher configuration through Android managed-device/device-owner and kiosk approaches.

A key distinction is that a simplified interface is not the same thing as administrative control, and developer mode is not equivalent to device administration.

The desired security model is approximately:

Microphone → designated audio path → communication service

with unnecessary applications prevented from accessing the microphone where Android and the selected device permit this.

The project should not claim absolute microphone ownership for an ordinary Android application. System telephony, manufacturer DSP components, privileged services, and other operating-system functions may operate below the application layer.

## Community options rather than one required phone

A major conclusion from the conversation is that the project should serve a community in which people will arrive with different phones and different resources.

A practical future decision structure could therefore ask:

1. What phone does the person already have?
2. Is it supported, secure, functional, and compatible with the required cellular service?
3. Does it have a useful microphone/headset connection?
4. Does its existing voice processing provide sufficient quality?
5. Can a simple software configuration solve the accessibility problem?
6. If not, can a wired audio accessory solve it?
7. If not, would a VoIP implementation be appropriate?
8. If none of those work, is a purpose-built device justified?

This keeps the project from becoming dependent on one manufacturer's phone or one commercial service.

## Prototype sequence

The conversation suggested progressing from the least expensive and least invasive experiment toward custom hardware:

1. Test a simple wired headset with a close microphone.
2. Establish a baseline in realistic noisy environments.
3. Test candidate audio-processing software on recordings or a laptop.
4. Determine whether processing materially improves the remote listener's experience.
5. Test the selected audio path on the target Android phone.
6. Test failure and fallback behavior.
7. Only then design a smaller integrated accessory or phone case.
8. In parallel, investigate a separate VoIP version for situations where reliable data connectivity is acceptable.
9. Develop a supplier specification only after the necessary microphone, processor, power, connection, and performance requirements are measured.

## Safety and emergency communication

The project should preserve ordinary cellular emergency calling as an important fallback.

The conversation specifically rejected the idea that a data-only system should automatically become the sole communication path. A VoIP version can be useful, but the cellular telephone path should remain available where emergency calling is required.

Emergency behavior, carrier compatibility, VoLTE operation, accessory failure behavior, and locked-down-phone behavior must be tested rather than inferred.

## Guiding project principle

**Give people options for simple communication without forcing everyone into the same phone, network, software architecture, or hardware design.**

Move complexity into the system where it can be tested and maintained, while keeping the person's actual interaction as simple and dependable as possible.

## Evidence boundary

This summary records the direction and reasoning developed in the conversation. It does not by itself establish that a particular Android phone, carrier, accessory, algorithm, or emergency-calling configuration will work.

The separate research-background document should remain the source for the documented/reported/inference distinctions and the cited technical and regulatory material.
