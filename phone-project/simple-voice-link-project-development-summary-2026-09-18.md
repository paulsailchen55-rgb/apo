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

## AI secretary and telephone-bridge architecture

A later branch of the conversation changed the architectural question in an important way: the simplest phone does not necessarily have to call a particular person directly.

One possible architecture is:

```
Person
  ↓
Simple phone / one-button interface
  ↓
Telephone number
  ↓
AI secretary / communication intermediary
  ↓
Person, service, organization, or other telephone number
```

In this model, the person's endpoint can remain extremely simple while more of the complexity lives behind the telephone number.

### The simple endpoint

The endpoint could still be the small, independently connected phone described elsewhere in this project. A person might press one large button and say, for example, that they want to talk to a particular person.

The endpoint does not necessarily need to know how the eventual connection is established. It only needs a dependable way to reach the intermediary and carry intelligible two-way speech.

This preserves the original accessibility goal: the complexity of the communication system can be moved away from the person who has difficulty operating a conventional smartphone.

### The AI secretary as an intermediary

The intermediary could answer the telephone number and conduct a simple conversation with the caller.

Potential functions discussed include:

- Identify who the caller wants to reach.
- Connect or bridge the caller to an authorized person.
- Handle requests to call another number.
- Help schedule events or appointments.
- Explain what is happening during a call.
- Remember or retrieve authorized communication information where appropriate.
- Handle ordinary telephone interactions that would otherwise require a person to navigate menus or applications.
- Provide a conversational interface to other services.

These are architectural possibilities, not claims that a particular service currently provides all of them.

The important design idea is that the telephone number becomes an access point to a communication service rather than merely a fixed endpoint.

### Telephone menus, keypad input, and DTMF

The design should retain conventional telephone controls rather than assuming that everything can be accomplished through speech.

DTMF—the familiar tones generated by telephone keypad digits—is a longstanding mechanism for interacting with automated telephone systems. IETF RFC 4733 specifies a standardized way to carry DTMF and other telephone events in RTP-based systems, and explicitly discusses gateways that pass DTMF to IVR systems. citeturn0search1turn0search3

This matters for accessibility because a person may sometimes need to press a number rather than speak, and because many existing telephone systems still require keypad responses.

The architecture should therefore allow at least three forms of interaction where technically appropriate:

1. Spoken commands.
2. Physical or on-screen keypad/DTMF commands.
3. Ordinary two-way speech with another person after the connection is established.

The AI intermediary should not make conventional telephone interoperability disappear.

### Call bridging and reconnection

A useful extension is for the intermediary to become a telephone bridge.

For example:

```
Caller
  ↓
AI secretary
  ↓
Person A

or

Caller
  ↓
AI secretary
  ↓
Person B

or

Caller
  ↓
AI secretary
  ├── Person A
  └── Person B
```

The last case represents a possible three-way or conference-style connection. More generally, the intermediary could maintain the communication session while changing which authorized endpoint is connected.

This is not a new fundamental telephone concept. SIP/PSTN systems already provide mechanisms for gateways, call routing, keypad input, and interaction with telephone applications. RFC 5629 describes a model in which a remote server-side user interface can receive speech and keypad input from a telephone client and derive user intent; modern commercial telephony platforms likewise expose mechanisms for SIP/PSTN connectivity and changing calls in progress. citeturn0search2turn0search9

The project question is therefore less “can telephone bridging exist?” and more “what is the smallest, safest, most accessible implementation that gives this particular user the desired experience?”

### AI does not have to own the whole telephone system

The AI secretary should be treated as one layer rather than as the entire system.

A possible layered architecture is:

```
[Simple user endpoint]
        ↓
[Telephone / VoIP transport]
        ↓
[Call-control and bridge layer]
        ↓
[AI secretary]
        ↓
[Authorized tools and services]
        ↓
[People / organizations / other telephone endpoints]
```

This separation is important.

The telephone transport should remain understandable and testable independently of the AI. Call control should remain capable of enforcing permissions and connection rules. The AI should operate within those boundaries rather than being trusted with unrestricted control over every communication function.

For example, an AI might be allowed to request that a call be connected, but the bridge layer could determine which numbers are authorized and whether a particular action is permitted.

### A practical development path

The AI-secretary idea does not need to be implemented before the simpler phone prototype is useful.

A staged path could be:

1. Establish the one-button endpoint and reliable speech.
2. Test the microphone and competing-speaker isolation problem.
3. Establish a normal telephone connection.
4. Test a simple intermediary that answers a number and forwards a call.
5. Add spoken identification of the requested person.
6. Add DTMF/keypad fallback.
7. Add controlled call transfer or bridging.
8. Add scheduling or other narrowly defined tools.
9. Test authentication, authorization, privacy, logging, and failure behavior.
10. Only then consider a more general-purpose conversational secretary.

This keeps the accessibility hardware project from becoming dependent on an ambitious AI system.

### Current technology makes the architecture technically plausible

This general architecture is no longer merely hypothetical at the level of basic telephony plumbing. Current commercial platforms document direct connections between telephone networks and real-time speech-to-speech AI systems. Twilio, for example, currently documents bidirectional audio streaming between PSTN calls and OpenAI real-time voice systems, as well as SIP connections to real-time AI endpoints. citeturn0search0turn0search6

That evidence establishes that telephone-to-real-time-AI integration is technically available as a platform capability. It does not establish that such a service is appropriate for this project, that it satisfies accessibility or privacy requirements, or that it provides the exact secretary/bridge behavior envisioned here.

The project should therefore distinguish three different questions:

- **Technical possibility:** Can telephone audio reach an AI and return as telephone audio? Current documented systems show that it can. citeturn0search0turn0search6
- **System design:** Can that capability be constrained into a reliable secretary and call-bridge architecture? This requires design and testing.
- **User suitability:** Is the resulting system simple, dependable, affordable, private, accessible, and safe for the intended person? This remains an open project question.

### Edge or home-based secretary

The conversation also explored a longer-term possibility in which some or all of the secretary function could live on an edge device in the person's home rather than entirely in a remote cloud service.

Conceptually:

```
Telephone number
      ↓
Home/edge communication computer
      ↓
Local secretary
      ├── telephone bridge
      ├── household devices
      ├── authorized contacts
      └── external AI services
```

A local system could potentially answer the telephone number, maintain authorized contact information, perform some speech processing locally, and call external AI systems only when additional capabilities are needed.

This is a research direction, not a recommendation to deploy a home server. It introduces its own requirements for power, networking, security, maintenance, backups, software updates, privacy, and failure recovery.

### The secretary as a translation layer between people and complex AI

Another speculative direction is to use the secretary as a human-scale interface to more powerful AI systems.

Instead of asking a person to operate a complicated AI application, the person could speak naturally to the secretary. The secretary could then invoke authorized AI or software services and translate the resulting complexity back into a simple spoken conversation.

Conceptually:

```
Person
  ↓
Simple voice interaction
  ↓
Secretary
  ↓
Authorized AI / software tools
  ↓
Secretary
  ↓
Simple voice response
```

The secretary therefore becomes an interface layer between a person and systems that may otherwise be too complicated to operate directly.

This idea raises substantial questions about permissions, identity, privacy, record retention, hallucinations or incorrect actions, and the boundary between conversational assistance and taking real-world actions. Those questions should be treated as part of the architecture rather than postponed until after implementation.

### A more speculative future direction: machine-to-secretary interfaces

The conversation also raised a further speculative possibility: AI systems themselves might eventually be able to configure or negotiate interfaces through a secretary layer.

In that model, the secretary would not only translate between a human and a machine. It could become a stable communication interface through which different AI or software systems request services, exchange structured information, or establish authorized communication channels.

This is an exploratory research concept only. It should not be treated as an existing standard or deployed capability.

### Security and authority boundaries

The more capable the secretary becomes, the more important it is to separate conversation from authority.

A voice request such as “call John” is relatively low risk if the system is only choosing among authorized contacts. A request such as “send this document,” “change my appointment,” “give this person access,” or “purchase something” has a different risk profile.

A future architecture should therefore distinguish at least:

- What the caller is allowed to ask.
- What the AI is allowed to understand.
- What the AI is allowed to request.
- What the telephone bridge is allowed to connect.
- What external tools are allowed to do.
- Which actions require confirmation.
- Which actions require authentication stronger than voice alone.
- What information is retained and for how long.
- What happens when the AI is uncertain.

This principle also supports the original accessibility goal: the user should not have to understand the entire underlying system, but the system itself must maintain clear authority boundaries.

### Failure modes and fallback

The secretary architecture introduces new failure modes that do not exist in a direct one-button telephone.

Examples include loss of internet service, AI service outage, speech-recognition failure, incorrect identification of the requested contact, unwanted call transfer, account compromise, unauthorized access to call records, bridge failure, or a conversational system misunderstanding an instruction.

The project should therefore preserve a fallback path wherever practical.

A useful architectural distinction is:

```
Simple phone
   ↓
Direct/ordinary telephone capability
        OR
   intermediary/AI capability
```

The AI layer should add capability without becoming the only means by which the person can communicate.

### Research questions created by this branch

The AI-secretary branch creates a separate research track within Simple Voice Link:

- What telephone-number services can receive and place ordinary PSTN calls?
- Which services support real-time bidirectional audio?
- Which support SIP?
- Which support DTMF reliably?
- Which support call transfer, conferencing, or controlled bridging?
- Can a simple endpoint retain ordinary cellular service while using the AI secretary as an optional destination?
- Can the secretary maintain an allow-list of contacts?
- How should caller identity be established?
- What authentication is required for sensitive actions?
- What information should be stored locally versus remotely?
- Can speech processing occur locally for privacy or reliability?
- What happens when the AI is unavailable?
- What is the minimum monthly cost for a usable system?
- Can the system be built with open-source or self-hosted components?
- What licenses, terms of service, and data-use restrictions apply to each component?
- Can the system be made accessible to people with limited technical skills without making the underlying architecture unsafe?

These questions should be investigated separately from the microphone/noise-isolation research, because they concern the communication service architecture rather than only the endpoint hardware.

## How the project now fits together

The conversation can now be understood as several layers of one project rather than as competing ideas:

```
Layer 1 — Human interface
One button, simple handset, simple voice interaction

Layer 2 — Audio
Microphone placement, noise suppression, competing-speech isolation,
echo control, headset/accessory options

Layer 3 — Endpoint
Android phone, dedicated device, managed device, or purpose-built handset

Layer 4 — Transport
Ordinary cellular telephone, VoIP, SIP, or another telephone connection

Layer 5 — Communication intermediary
Optional forwarding, call routing, bridge, conference, or AI secretary

Layer 6 — Tools
Scheduling, authorized contacts, external services, databases, and other
carefully permissioned functions

Layer 7 — Advanced AI interface
Optional connection to larger AI systems through the secretary

Layer 8 — Future machine interfaces
Speculative interfaces among AI/software systems through stable
communication intermediaries
```

The key architectural insight is that these layers do not all have to be built at once.

A person could use only Layers 1–4. Another person might use Layers 1–5. A later version could add Layers 6–7. The speculative Layer 8 can remain a research direction without affecting the basic telephone.

This layered model also preserves an important principle from the earlier work: do not make the person carry the complexity merely because the technology underneath has become complex.

## Status of this section

The AI-secretary and telephone-bridge material is a combination of conversation-derived architecture, documented current telephony capabilities, and speculative future concepts.

The documented technical claims about DTMF, SIP interaction, PSTN bridging, and current telephone/AI integrations are supported by the cited standards and platform documentation. The specific Simple Voice Link architecture, permission model, edge-AI arrangement, and future machine-to-secretary concept remain project proposals requiring design, testing, and independent verification.


## Evidence boundary

This summary records the direction and reasoning developed in the conversation. It does not by itself establish that a particular Android phone, carrier, accessory, algorithm, or emergency-calling configuration will work.

The separate research-background document should remain the source for the documented/reported/inference distinctions and the cited technical and regulatory material.
