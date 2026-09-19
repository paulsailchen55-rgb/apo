## Research terms worth pursuing

Here is the full list from the existing Simple Voice Link notes. I’ll keep each explanation brief and give you questions to react to. We can treat your answers as the beginning of the research discussion rather than trying to answer everything immediately.

### 1. Speaker recognition / speaker verification

Speaker recognition concerns extracting characteristics from someone's voice to determine who is speaking. Speaker verification is the narrower question: “Is this voice consistent with the claimed person?”

Questions:

- What parts of a person's voice are actually being measured?
- How much of the identification comes from the voice itself versus the microphone, room, or telephone connection?
- Could this work when other people are speaking simultaneously?
- How much does someone's voice change with age, illness, fatigue, emotion, or a different microphone?
- Would we want this to identify the person, or merely contribute one piece of evidence?

### 2. Presentation attack detection (PAD)

Presentation attack detection asks whether the system is being presented with something intended to fool its sensor—for example, a recording, playback device, or artificial signal instead of a live person.

Questions:

- How would the system distinguish a live person from a recording?
- What happens if someone plays the person's voice through a very good speaker?
- Could the system detect that the sound originated from a speaker rather than a human mouth?
- Could our room/acoustic-response idea help?
- Could a physical token provide a separate signal that a recording cannot reproduce?

### 3. Voice anti-spoofing

Voice anti-spoofing is the broader effort to prevent authentication systems from being fooled by replayed, synthesized, converted, or otherwise manipulated speech.

Questions:

- What kinds of attacks should we actually assume?
- Replay of a recording?
- AI-generated speech?
- Voice conversion?
- Direct digital injection into the audio stream?
- Could a fresh conversational challenge make prerecorded responses less useful?
- Could the system combine voice anti-spoofing with the physical authentication token?

### 4. Replay attack detection

Replay attack detection specifically concerns detecting previously recorded legitimate audio being played back to the system.

Questions:

- What characteristics distinguish a live voice from a recording?
- Can the system detect speaker, room, loudspeaker, or microphone artifacts?
- Would asking the person to respond spontaneously to a changing challenge help?
- Could an acoustic room-response measurement reveal that the voice is coming from the wrong physical location?
- How close to the microphone would the attacker have to be?

### 5. Audio injection attack detection

Audio injection is different from an ordinary replay: instead of physically playing a recording into the microphone, an attacker may attempt to introduce manipulated digital audio directly into the audio-processing chain.

Questions:

- Where are the possible injection points?
- Microphone?
- USB/headset connection?
- Android audio subsystem?
- Telephone network?
- AI-secretary server?
- Could cryptographic authentication survive even if the audio itself were compromised?
- Should the phone and secretary authenticate each other independently of the voice?

### 6. Acoustic sensing

Acoustic sensing uses sound as a measurement tool rather than merely as communication.

Questions:

- What can the microphone learn about the surrounding environment?
- Can sound reveal that a person is physically present?
- Can it distinguish one room from another?
- Can it detect movement?
- Can it detect the distance between the person and the phone?
- Could the phone deliberately make a sound and listen to the response?

### 7. Room impulse response (RIR)

A room impulse response describes how an acoustic signal changes as it travels through a particular room and reflects from walls, furniture, people, and other objects.

Questions:

- Could the room itself become part of the authentication evidence?
- If Paul is standing in a particular room, does the acoustic response have a recognizable pattern?
- What happens when another person enters the room?
- How stable is the pattern when furniture moves?
- Could an attacker reproduce the expected acoustic environment somewhere else?

### 8. Acoustic scene analysis

Acoustic scene analysis attempts to characterize what is happening in an acoustic environment—for example, speech, traffic, music, machinery, or other sounds.

Questions:

- Could the secretary determine whether the user is actually in the expected environment?
- Could it recognize “home,” “group home,” outdoors, vehicle, etc.?
- Could scene information help distinguish a legitimate call from an artificial recording?
- How much privacy would continuous environmental analysis create?
- Can the system analyze the environment without permanently recording it?

### 9. Device-free localization

Device-free localization attempts to locate or detect a person without requiring that person to carry a dedicated tracking device.

Questions:

- Could the phone determine where the person is relative to it using sound?
- Could it tell whether someone is standing, sitting, approaching, or moving away?
- Could this establish physical presence?
- Could it distinguish the authorized person from another nearby person?
- Does this require active sound emission, or can it work passively?

### 10. Human presence detection by acoustics

This asks whether acoustic measurements can determine that a human is physically present even when the person isn't speaking.

Questions:

- Can the system detect a silent person?
- Could breathing, movement, body reflections, or changes in room acoustics provide evidence?
- Could this help prevent someone from simply playing a recording?
- How reliably could this work with ordinary inexpensive hardware?
- What happens when two people are present?

### 11. Non-line-of-sight acoustic sensing

Non-line-of-sight acoustic sensing investigates whether sound reflections or other acoustic information can reveal objects or people that aren't directly visible to the sensor.

Questions:

- Could the phone detect someone who is around a corner or behind an obstruction?
- Could reflected sound reveal body position?
- Could this be useful for authentication or only for localization?
- How much does the room have to be known beforehand?
- Could this create unwanted surveillance capabilities that we should explicitly avoid?

### 12. Active acoustic sensing

Active acoustic sensing means the device deliberately emits a known signal and measures what comes back.

Questions:

- What if the phone says, in effect, “send out this tiny signal and listen to the room”?
- Could the response establish physical presence?
- Could a very short-range token respond to that signal?
- Could we use different frequencies or patterns for different purposes?
- Could the physical authentication token participate in the challenge-response itself?

### 13. Ultrasonic localization

Ultrasonic localization uses sound above the ordinary human hearing range to determine position, distance, or movement.

Questions:

- Could an ultrasonic signal establish that the token is physically close to the microphone?
- What frequency range is actually practical?
- Does anything special happen as we approach the 300 kHz region?
- What sensors would be required?
- Could the phone's existing microphone detect it, or would we need a separate sensor?

### 14. Acoustic imaging

Acoustic imaging uses arrays of microphones or other acoustic sensors to construct spatial information about sound sources or reflected sound.

Questions:

- Could an array distinguish the intended speaker from several competing speakers?
- Could it locate the speaker relative to the phone?
- Could it identify the shape or position of objects through their acoustic reflections?
- How many microphones would be necessary?
- Could a tiny wearable device accomplish anything useful with an array?

### 15. Microphone-array sensing

Multiple microphones can provide spatial information that a single microphone cannot.

Questions:

- How much does two microphones buy us?
- What about four, six, or more?
- Could an array determine which person is speaking?
- Could it steer toward the intended speaker?
- Could it simultaneously provide localization and noise/speech separation?
- How small can the array become?

### 16. Beamforming and blind source separation

Beamforming combines signals from multiple microphones to emphasize sound arriving from particular directions. Blind source separation attempts to separate overlapping sound sources without necessarily knowing beforehand what each source sounds like.

Questions:

- Could we isolate one person while several people are talking?
- Does knowing approximately where the intended speaker is make the problem easier?
- Could the physical design of the phone or headset do most of the work before AI processing?
- How much processing power is required?
- Could this be done locally on an inexpensive Android device?

### 17. Acoustic transfer function

An acoustic transfer function describes how sound is transformed between a source and a receiver by the intervening physical system.

Questions:

- Does the person's body create a measurable transfer function?
- Does the distance between mouth, body, token, and microphone matter?
- Could that transfer function become part of an authentication signature?
- How stable is it when the person moves?
- Could clothing, posture, room, or microphone position overwhelm the person's individual characteristics?

### 18. Body-induced acoustic reflections

A person's body can alter sound through reflection, absorption, diffraction, and scattering.

Questions:

- Could those changes provide evidence that a particular person is actually near the microphone?
- Could different body shapes or positions produce measurable differences?
- Could this work without the person speaking?
- Would ordinary speech itself provide enough excitation, or would active sensing be better?
- Could an attacker reproduce the reflection pattern?

### 19. Physiological acoustics

Physiological acoustics studies sounds or vibrations generated by the body, including things such as heart sounds, respiration, movement, and other physiological processes.

Questions:

- Which body-generated signals are actually measurable outside the body?
- Which require physical contact?
- Could the same microphone capture speech and some physiological information?
- Would an ear-mounted or body-contact sensor be more useful?
- Which signals are stable enough to contribute to authentication?

### 20. Heart-sound biometrics

Heart-sound biometrics investigates whether cardiac sounds contain information that can distinguish people.

Questions:

- What sensor is required to capture heart sounds reliably?
- Could an earbud, headset, or body-contact device capture them?
- How much do heart sounds vary with exercise, illness, stress, or posture?
- Would heart sounds be an identity signal, a liveness signal, or simply another piece of evidence?
- Could an attacker reproduce them?

### 21. In-ear heart-sound authentication

This is a more specific approach in which an in-ear sensor can potentially capture physiological sounds or vibrations while the person is wearing an ear device.

Questions:

- Could one device simultaneously handle the person's voice and physiological signal?
- Would an earbud be acceptable for someone who needs a very simple phone?
- Could this be passive, or would it need an active sensor?
- What happens when the person removes the ear device?
- Could this provide stronger evidence of physical presence than an ordinary microphone?

### 22. ECG biometric authentication

ECG authentication uses electrical measurements of the heart rather than acoustic measurements.

Questions:

- Could a wearable device obtain a sufficiently reliable ECG?
- Does ECG provide something fundamentally different from voice?
- Would skin-contact electrodes be practical for this project?
- Could the ECG merely establish liveness rather than identity?
- How should the system behave if the physiological signal is temporarily unavailable?

### 23. Multimodal biometric fusion

Multimodal fusion means combining multiple kinds of evidence rather than relying on one biometric.

Questions:

- What combination actually gives us independent information?
- Voice + token?
- Voice + acoustic environment?
- Voice + physiology?
- Token + voice + physical presence?
- How should the system respond when two signals disagree?
- Should one strong signal be enough, or should several weaker signals have to agree?

### 24. Behavioral biometrics

Behavioral biometrics examines characteristics of how someone acts rather than a fixed physical characteristic.

This connects directly to your body-generated-sound idea: the timing, force, rhythm, and manner in which someone performs an action might potentially become an identifying signal.

Questions:

- Could a person's habitual sounds or movements be sufficiently characteristic?
- Which behaviors are stable?
- Which can be deliberately changed?
- Could a changing behavioral challenge be used?
- How much observation would an attacker need to learn the pattern?
- Does this create unacceptable surveillance risks?

### 25. Continuous authentication

Continuous authentication means the system continues evaluating whether the authorized person remains present rather than authenticating only once.

Questions:

- Does the system need to authenticate only when a call starts?
- Or should it continue checking during a conversation?
- Could continuous checking become annoying or invasive?
- Could the physical token establish the session initially and the other sensors merely monitor for unexpected changes?
- What should happen if confidence suddenly drops?

### 26. Challenge-response biometrics

A challenge-response system gives the person something new to respond to instead of asking for the same permanent response every time.

Questions:

- Could the secretary generate a fresh spoken challenge?
- Could the person answer naturally?
- Could the challenge involve a body-generated sound or physical gesture?
- Could the token cryptographically respond to the same challenge?
- How do we prevent someone from recording enough previous interactions to predict future responses?

### 27. Sensor/endpoint integrity

This concerns whether we can trust the device that is doing the sensing.

Questions:

- How do we know the microphone is really the microphone we intended to use?
- Could another application intercept or modify the audio?
- Could the operating system alter the signal?
- Could a compromised phone fake the authentication result?
- Should the phone itself have a cryptographic identity?
- Could the token and phone mutually authenticate before the secretary trusts either one?

### 28. Cryptographic device-bound authentication

This uses a secret/private key stored in a particular physical device rather than relying solely on something a person knows or something a biometric system observes.

Questions:

- Could the one-button phone have its own cryptographic identity?
- Could the companion token have another one?
- Could both have to be present?
- Can the private key be kept in secure hardware?
- What happens when the device is lost?
- How do we revoke and replace it without making the user manage complicated credentials?

### 29. And now, the new in-band audio/steganography branch

This is the newer idea we just added to the project: take information generated locally—potentially from the high-frequency token—and encode a very small authenticated payload into the ordinary audio traveling through the cellular call.

Questions:

- What kinds of audio modulation survive cellular voice codecs?
- Can we hide a small cryptographic challenge/response without noticeably changing the voice?
- Which parts of the audio spectrum are actually reliable?
- Would phase, amplitude, timing, spread-spectrum, or another technique work best?
- Can the secretary reliably extract the data after noise suppression, AGC, codec compression, and transcoding?
- Could the carrier/network accidentally destroy the hidden signal?
- Can the system detect deliberate injection or replay of the hidden signal?
- How many bits do we actually need to transmit?
- Could the entire 300 kHz concept remain local to the phone/token while only its cryptographic result travels through the ordinary call?

The last question is probably the most important architectural one to investigate experimentally: **the high-frequency sensor and the cellular audio channel may not need to be the same physical signal path at all.**
