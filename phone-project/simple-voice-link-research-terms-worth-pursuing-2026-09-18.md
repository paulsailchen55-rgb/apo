# Simple Voice Link — Research Terms Worth Pursuing

**Date:** 2026-09-18  
**Status:** Conversation-derived research map for readers and further discussion. These entries identify research directions; they do not establish that any proposed authentication method is technically validated.

This document is a compact, reader-friendly map of the research terms that emerged while developing the Simple Voice Link authentication and acoustic-sensing ideas. Each term has a short description followed by questions that can guide further investigation.

## 1. Speaker recognition / speaker verification

Speaker recognition asks whether a system can distinguish speakers from their voices. Speaker verification is the narrower question of whether a voice matches a claimed identity.

Questions:
- What parts of speech carry speaker-specific information?
- How stable are those features across illness, fatigue, aging, emotion, microphones, rooms, and background noise?
- How well do current systems resist replay or synthesized speech?
- Where does speaker verification belong in a broader authorization system?

## 2. Presentation attack detection (PAD)

Presentation attack detection asks whether biometric input is genuine or is being presented through an attack, such as a recording, replay device, mask, or other artifact. It is important because recognition alone does not establish that the real person is present.

Questions:
- What attacks matter for voice and acoustic authentication?
- How can a system distinguish live input from replay?
- Which sensors or signals provide useful liveness evidence?
- Can PAD operate without continuous recording?

## 3. Voice anti-spoofing

Voice anti-spoofing focuses specifically on detecting attempts to fool voice systems using replayed, converted, synthesized, or otherwise manipulated speech. It overlaps with PAD but emphasizes the speech-generation threat.

Questions:
- What current spoofing techniques are most effective?
- How do anti-spoofing systems behave with ordinary telephone audio?
- How much information is lost through cellular codecs?
- Can anti-spoofing be combined with a physical cryptographic token?

## 4. Replay attack detection

Replay detection asks whether a microphone is hearing a recording rather than a live event. This is especially important when voice or body-generated sounds are used for authentication.

Questions:
- What acoustic traces distinguish live speech from loudspeaker playback?
- Can room response, microphone characteristics, or challenge-response help?
- How do replay attacks change when the attacker has a high-quality recording?
- Can replay detection work over ordinary cellular calls?

## 5. Audio injection attack detection

An injection attack does not necessarily require a speaker in the room. Audio could potentially be inserted directly into an audio path, device, application, or communication stream.

Questions:
- At what points in the phone/audio chain could injection occur?
- What evidence could reveal that audio did not originate at the intended microphone?
- Can hardware-backed trust help distinguish local microphone input from software-injected audio?
- What should happen when the system cannot establish signal provenance?

## 6. Acoustic sensing

Acoustic sensing treats sound not merely as speech but as information about objects, movement, spaces, and physical events. This is the broad field behind many of the later ideas in this project.

Questions:
- What can a microphone measure besides speech?
- Which environmental and body-related signals are measurable at short range?
- What can passive sensing detect versus active sensing?
- What information survives ordinary phone hardware?

## 7. Room impulse response (RIR)

A room impulse response describes how a sound changes as it travels through a space and reflects from surfaces. Because people alter that acoustic field, RIR measurements can potentially provide information about occupancy, position, or environmental change.

Questions:
- How much does a person's presence alter an RIR?
- Can RIR features support liveness or proximity detection?
- How stable is an RIR across furniture, doors, temperature, and other changes?
- Can a phone measure useful room-response information without specialized hardware?

## 8. Acoustic scene analysis

Acoustic scene analysis attempts to characterize an environment from its sounds: speech, traffic, machinery, music, rooms, and other acoustic events. It could provide context for an authentication system.

Questions:
- Can the system recognize that it is in an expected environment?
- Could scene information help distinguish a genuine interaction from a replay?
- How much environmental information should be retained?
- How can privacy be protected when the environment itself becomes a sensor?

## 9. Device-free localization

Device-free localization attempts to detect or locate people without requiring them to carry a dedicated tracking device. Acoustic reflections and changes in propagation can be one sensing mechanism.

Questions:
- Can a phone determine whether a person is nearby without a wearable?
- What spatial resolution is realistic?
- Can this be limited to very short range?
- How can unintended people in the same room be excluded?

## 10. Human presence detection by acoustics

Human presence detection asks whether a person is physically present based on acoustic changes, even when the person is not speaking. This connects directly to the idea that the body changes the acoustic field.

Questions:
- Can a silent person be detected reliably?
- Which signals are most useful: reflections, movement, breathing, or room response?
- How vulnerable is the method to objects moving in the same space?
- Could presence be used as one factor rather than as identity by itself?

## 11. Non-line-of-sight acoustic sensing

Non-line-of-sight sensing investigates whether sound can provide information about people or objects that are not directly visible to the sensor. Reflections and indirect paths become part of the measurement.

Questions:
- What can indirect acoustic paths reveal?
- What range and geometry are practical?
- Could NLOS sensing provide additional evidence of physical presence?
- What are the privacy implications of sensing around corners or through barriers?

## 12. Active acoustic sensing

Active acoustic sensing deliberately emits a known signal and measures what comes back. The known stimulus can make it possible to estimate changes in the environment.

Questions:
- What signal should be emitted?
- What frequencies and power levels are practical and safe?
- How much information can be extracted from the response?
- Could an authentication device issue a fresh acoustic challenge?

## 13. Ultrasonic localization

Ultrasonic localization uses frequencies above the ordinary human hearing range to estimate position, distance, or proximity. It is relevant to the proposed very-short-range token.

Questions:
- What ultrasonic frequencies can ordinary phones actually receive?
- What specialized sensors are needed for higher frequencies?
- How short can the useful range be made?
- How resistant is the channel to replay, relay, and injection?

## 14. Acoustic imaging

Acoustic imaging uses arrays and signal processing to infer spatial information from sound. It can be thought of as constructing a picture of an acoustic field rather than a conventional optical image.

Questions:
- What spatial detail is possible with small microphone arrays?
- Can body position or movement be resolved?
- What happens in reverberant rooms?
- Could acoustic imaging provide useful liveness or proximity evidence?

## 15. Microphone-array sensing

Multiple microphones provide spatial information that one microphone cannot easily provide. Arrays can support direction finding, beamforming, source separation, and environmental measurement.

Questions:
- How many microphones are actually useful?
- What array geometry works in a phone, watch, headset, or token?
- How much does microphone mismatch matter?
- Could a small array isolate one nearby speaker from competing speakers?

## 16. Beamforming and blind source separation

Beamforming combines signals from multiple microphones to emphasize a direction. Blind source separation attempts to separate overlapping sources without already knowing exactly what each source contains.

Questions:
- How well can competing human voices be separated?
- What happens with only two or three microphones?
- Which processing can run in real time on a low-power Android device?
- How do reverberation and moving speakers affect separation?

## 17. Acoustic transfer function

An acoustic transfer function describes how a signal changes between a source and a receiver through a physical path. It can include effects from distance, surfaces, objects, microphones, and the environment.

Questions:
- Can an individual's presence alter a measurable transfer function?
- Can a short-range token use the transfer function as part of authentication?
- How stable is it over time?
- Could an attacker reproduce or relay it?

## 18. Body-induced acoustic reflections

A person's body changes the way sound propagates and reflects in a space. Those changes may contain information about position, movement, anatomy, and interaction with nearby surfaces.

Questions:
- Which body parts produce useful acoustic changes?
- How much of the effect is individual-specific?
- Can reflections distinguish one person from another?
- Could this provide liveness evidence without relying on speech?

## 19. Physiological acoustics

Physiological acoustics studies sounds generated by or associated with the body, including speech, breathing, heart sounds, movement, and other physical processes.

Questions:
- Which body-generated sounds can be captured without contact?
- Which require contact, near-body, or specialized sensors?
- Which signals are stable enough for authentication?
- Which should be treated as health measurements rather than identity signals?

## 20. Heart-sound biometrics

Heart-sound biometrics investigates whether cardiac sounds can contribute to identifying a person. This is distinct from ordinary voice authentication.

Questions:
- How individual-specific are heart sounds?
- What sensors and contact arrangements are required?
- How stable are measurements over time and physical condition?
- Can heart sounds provide liveness rather than identity alone?

## 21. In-ear heart-sound authentication

In-ear systems place a sensor close to the ear and can potentially capture body-conducted or near-body physiological signals. Research has explored heart-related signals in this setting.

Questions:
- What can an earbud or in-ear sensor actually measure?
- Is contact necessary?
- Could the same device provide speech, physiological, and cryptographic functions?
- What are the privacy and failure implications?

## 22. ECG biometric authentication

ECG biometric authentication uses electrical cardiac signals as an identity-related measurement. ECG is substantially different from trying to hear a heartbeat through an ordinary airborne microphone.

Questions:
- What makes ECG measurements distinctive?
- What electrode placement is practical for a simple device?
- How does physical activity affect the signal?
- Could ECG be one factor in a multimodal system rather than a standalone credential?

## 23. Multimodal biometric fusion

Multimodal fusion combines evidence from multiple biometric or physical channels. In this project, possible channels include voice, acoustic presence, physiology, behavior, and a cryptographic device.

Questions:
- How should conflicting signals be handled?
- Which combinations actually improve security?
- How can the system avoid collecting unnecessary biometric data?
- Should different actions require different levels of evidence?

## 24. Behavioral biometrics

Behavioral biometrics uses patterns in how a person acts rather than only fixed physical traits. Speech rhythm, movement, interaction patterns, and potentially body-generated sounds fit into this broader area.

Questions:
- Which behaviors are sufficiently stable to measure?
- How much does fatigue, injury, age, or context change them?
- How vulnerable are behavioral patterns to observation and imitation?
- Can behavioral evidence be used without creating continuous surveillance?

## 25. Continuous authentication

Continuous authentication attempts to maintain confidence that the authorized person remains present throughout a session rather than checking identity only once.

Questions:
- Is continuous authentication necessary for this project?
- Could it create unacceptable privacy or battery costs?
- Can occasional short checks replace continuous monitoring?
- What happens when confidence drops during an ongoing call?

## 26. Challenge-response biometrics

Challenge-response authentication changes the interaction so that an attacker cannot simply replay a previously recorded answer. A fresh challenge can require a fresh human response.

Questions:
- What kinds of acoustic or behavioral challenges are practical?
- Can a challenge be unpredictable but still accessible?
- How much does a fresh challenge reduce replay risk?
- How should challenge-response interact with a device-held cryptographic secret?

## 27. Sensor/endpoint integrity

Sensor integrity asks whether the system can trust the microphone, sensor, operating system, and endpoint that produced the evidence. Authentication is weaker if an attacker can replace or manipulate the input before verification.

Questions:
- Can Android establish trustworthy microphone provenance?
- What can hardware-backed security contribute?
- How should compromised or modified phones be handled?
- Can the system detect when the expected sensor has been replaced or bypassed?

## 28. Cryptographic device-bound authentication

A cryptographic device-bound credential is a secret held by a device rather than something that has to be spoken or remembered. The proposed physical token belongs in this category.

Questions:
- Can a small token prove possession of a private key without revealing it?
- How should freshness, revocation, and recovery work?
- Could acoustic proximity carry the challenge-response exchange?
- How should the cryptographic factor combine with human-presence or behavioral evidence?

## 29. In-band audio / steganography branch

This branch asks whether authentication information can be encoded into ordinary telephone audio so it survives a real cellular voice path. The key idea is that a local high-frequency or other physical signal does not necessarily have to travel through the cellular network in its original form; the phone could convert it into a small authenticated payload and embed that payload into an audio-band signal.

Questions:
- Which audio-steganographic or in-band data methods survive real cellular codecs?
- What happens after noise suppression, AGC, VAD, echo cancellation, resampling, packet loss, and transcoding?
- How many bits are actually needed for a cryptographic challenge-response?
- Can the system distinguish the embedded authentication signal from deliberate injection?
- Can the method work across different phones, carriers, codecs, and call paths?
- Does the method remain useful if the proposed 300 kHz local sensing channel turns out not to be practical?

## A useful way to read this list

These terms are not all parts of one required system. Some describe established research fields; some are possible components; and some are questions generated by the Simple Voice Link concept itself.

A useful experimental progression is:

1. Understand the ordinary voice channel.
2. Study speaker verification and anti-spoofing.
3. Study acoustic sensing and room/presence signals.
4. Study microphone arrays, beamforming, and source separation.
5. Study physiological and behavioral channels.
6. Study cryptographic device-bound authentication.
7. Test multimodal fusion.
8. Finally test whether any of these signals can be transported robustly through the actual telephone path.

The central research question is not “Can every proposed signal be used?” It is:

> What combination of simple human interaction, physical presence evidence, acoustic information, and cryptographic device authentication can produce a communication system that is both usable and meaningfully secure?

