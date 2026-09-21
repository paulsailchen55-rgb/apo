# Phone-Independent Personal Device Ecosystem

**Status:** Exploratory project ecosystem / evolving prototype architecture  
**Started:** 2026-09-21  
**Archive purpose:** Preserve the evolving concept as a coherent ecosystem rather than treating the watch, cellular band, camera, glasses, and phone as unrelated projects.

## 1. Core idea

The project is a personal technology ecosystem designed to let a person move through the world without having a smartphone as the primary interface.

The phone may still exist and remain useful, but it is no longer the central device that everything depends upon.

The ecosystem is intentionally distributed: each device does a limited job well, and the devices communicate with one another.

The current conceptual system is:

1. **Primary low-power watch** — the principal wearable interface.
2. **Separate cellular/eSIM connector band** — an independently switchable communications gateway.
3. **Pocketable high-quality camera/recorder** — a dedicated recording device.
4. **Text-based glasses** — an eventual private visual-output device.
5. **Phone** — optional supporting equipment rather than the center of the system.

## 2. Primary watch

The watch should remain useful as a watch even when the communications gateway is turned off.

The preferred direction is a very low-power, sunlight-readable display technology such as:

- Memory-in-Pixel (MIP)
- reflective LCD (RLCD)
- related transflective display technologies

The watch is envisioned as the human-facing interface for:

- time
- text
- messages
- AI interaction
- controls
- voice interaction
- selected health/sensor functions
- navigation or other contextual information

The current research direction has identified COROS APEX 4 and COROS NOMAD as interesting candidate hardware platforms because of their MIP displays, microphones, speakers, sensors, battery life, and outdoor-oriented design.

This is a candidate direction, not a decision that COROS hardware must be used.

## 3. Separate cellular/eSIM connector band

A key architectural development is to avoid putting cellular hardware directly into the primary watch.

Instead, a second wearable can function as a communications gateway:

**cellular network / eSIM -> connector band -> Bluetooth -> primary watch**

The connector band could contain:

- eSIM or equivalent cellular identity
- LTE/cellular modem
- antenna
- rechargeable battery
- Bluetooth Low Energy
- potentially GNSS/GPS
- potentially NFC

The connector band should be independently controllable. The wearer could turn it on when independent connectivity is wanted and turn it off when it is not.

This produces a deliberate two-wearable system:

- **watch = interface**
- **band = communications infrastructure**

The band does not have to be a conventional smart band with its own screen.

A screenless communications module may ultimately be preferable.

## 4. Why separate the cellular system?

Cellular radios, antennas, and associated processing consume substantially more power and impose physical design constraints.

Keeping those components separate could allow the primary watch to remain:

- thinner
- lower power
- more readable
- simpler
- useful for long periods without cellular connectivity

It also creates modularity: the same watch could potentially operate with or without the communications band.

The architectural question is whether a sufficiently capable cellular/Bluetooth wearable gateway can provide the needed communications without making the overall system cumbersome.

## 5. Bluetooth versus NFC

Bluetooth and NFC have different roles.

### Bluetooth

Bluetooth Low Energy is the likely continuous connection between the connector band and the primary watch.

Possible path:

**watch <-> Bluetooth <-> cellular band <-> cellular network**

### NFC

NFC is considered an additional short-range interaction layer rather than a replacement for Bluetooth.

Potential uses include:

- payments
- authentication
- access/control
- device pairing
- other tap-based interactions

The ecosystem should not assume that NFC is the primary communications channel.

## 6. Phone independence

The goal is not necessarily to eliminate the phone.

The goal is to eliminate **phone dependence**.

A person should be able to leave the phone behind and still have a useful personal communications system.

The phone can remain available for:

- large-screen work
- complex configuration
- applications that genuinely benefit from a phone
- backup
- charging/synchronization
- tasks that do not belong on the wearable system

But ordinary communication should not require carrying and constantly looking at a smartphone.

## 7. Pocketable camera / recorder

A second major component is a dedicated pocketable recording device.

The desired device is not simply a phone camera.

It should be designed specifically for recording and should be small enough to carry in a pocket.

Conceptual characteristics:

- excellent still photography
- excellent video
- high-quality microphones / environmental sound recording
- pocketable form factor
- handheld operation
- gimbal or mechanically stabilized camera system
- ability to point outward at the environment
- ability to orient toward the wearer
- ability to capture surrounding sound
- ability to participate in the larger ecosystem rather than becoming another phone

The user should be able to pull it from a pocket, hold it naturally, point it at something, and record without first turning a phone into a camera.

The camera could eventually communicate with the watch and cellular gateway so that recording, communications, metadata, AI assistance, and remote storage do not require a smartphone.

## 8. Text-based glasses

A later-generation component is a pair of glasses whose primary purpose is not to reproduce a smartphone screen.

The current concept is deliberately simpler:

**glasses that display/scroll text.**

Potential roles:

- private text display
- incoming-message display
- AI responses
- navigation/context
- captions
- prompts
- camera/recording status
- other short-form information

The glasses could become another output surface for the same distributed personal system.

## 9. Ecosystem architecture

The long-term architecture can be represented conceptually as:

    PERSON
       |
       +---------------- PRIMARY WATCH
       |                 MIP/RLCD display
       |                 microphone
       |                 speaker
       |                 controls
       |                 sensors
       |
       +---------------- CELLULAR BAND
       |                 eSIM
       |                 LTE
       |                 Bluetooth
       |                 battery
       |                 optional NFC/GNSS
       |
       +---------------- POCKET CAMERA
       |                 camera
       |                 gimbal
       |                 microphones
       |                 recording/storage
       |
       +---------------- TEXT GLASSES
       |                 private text output
       |
       +---------------- PHONE (OPTIONAL)
                         larger-screen computing

The devices should share information through defined interfaces rather than requiring every device to contain every capability.

## 10. One-Number / AI Secretary relationship

This ecosystem is related to the existing One-Number AI Secretary / Emergency AI Watch work in the APO archive.

The cellular band could provide the independent network connection required by a watch-based AI communications interface.

The primary watch could provide the human-facing voice/text interface.

The AI/One-Number service could provide:

- communication routing
- transcription
- semantic processing
- synthesized voice
- contact interaction
- information retrieval
- other assistant functions

Emergency communication remains a separate high-reliability requirement and must not be assumed to work merely because ordinary AI communications work.

## 11. Prototype strategy

A useful progression is:

### Prototype A — distributed proof of concept

Use an existing MIP watch plus an independent cellular/Bluetooth development device.

Goal: demonstrate:

**watch <-> Bluetooth <-> cellular gateway <-> network**

without modifying the watch hardware.

### Prototype B — wearable gateway

Reduce the development hardware into a practical screenless band.

Goal:

- comfortable
- rechargeable
- independently switchable
- cellular-connected
- Bluetooth-connected
- capable of supporting the watch without a phone

### Prototype C — integrated wearable ecosystem

Add the pocket camera and begin defining common device protocols.

### Prototype D — text glasses

Add a minimal text-only visual output device.

### Prototype E — purpose-built ecosystem

Determine whether an existing company such as COROS, Garmin, or another hardware partner could manufacture or collaborate on a purpose-built system.

## 12. Potential hardware partners

Current exploration includes:

### COROS

COROS is particularly interesting because its current wearable hardware includes MIP displays, microphones, speakers, sensors, and long battery life. A possible conversation is whether an existing COROS watch could serve as the interface while an independent cellular band supplies connectivity.

Potential candidate watches discussed:

- COROS APEX 4
- COROS NOMAD

### Garmin

Garmin remains a major potential partner because of its established wearable ecosystem, manufacturing infrastructure, integrations, sensors, and experience with long-battery outdoor devices.

The concept should not assume that Garmin or COROS will participate; they are potential routes for exploration.

## 13. Design principles

The ecosystem should follow several principles:

1. **No phone dependence.**
2. **Do not make every device a miniature phone.**
3. **Give each device a clear job.**
4. **Prefer low-power interfaces when full graphical displays are unnecessary.**
5. **Separate high-power communications from the low-power watch when useful.**
6. **Allow components to be turned on/off independently.**
7. **Use open or well-documented interfaces where practical.**
8. **Keep the system understandable to the person wearing it.**
9. **Preserve ordinary watch functionality even when communications are disabled.**
10. **Treat privacy, recording controls, security, and emergency reliability as first-class engineering requirements.**

## 14. Open research questions

- What existing cellular/eSIM wearable gateways can communicate reliably with a third-party watch over BLE?
- Can an eSIM cellular band maintain useful battery life while providing voice/data services?
- Which Bluetooth profiles/protocols are best suited to watch-to-gateway communications?
- Could a cellular gateway handle the network side while the watch handles microphone/speaker interaction?
- Which existing MIP/RLCD watches provide the most accessible development environment?
- How much of a COROS or Garmin watch can be controlled through documented APIs?
- Can NFC payments be implemented independently of the phone?
- What is the smallest practical cellular gateway battery?
- Could the gateway also provide GNSS?
- How should the camera communicate with the watch and gateway?
- What data should remain local?
- What should be encrypted?
- How should recording status be communicated visibly/audibly?
- How should emergency calling work if the phone is absent?
- What happens when the cellular band is turned off?
- What happens when the watch and band lose Bluetooth connection?
- Can the system gracefully fall back to phone connectivity when the phone is available?
- What are the best existing technologies for simple text-only glasses?

## 15. Current conceptual summary

The project is a **distributed personal device ecosystem**, not a replacement smartphone.

The central idea is to separate functions that smartphones have historically combined:

**watch = human interface**

**cellular band = independent connectivity**

**camera = recording**

**glasses = private text output**

**phone = optional general-purpose computer**

The intended result is a person who can walk through the world with a small set of specialized devices, communicate and interact with an AI/One-Number service without continuously carrying or looking at a phone, record the world with a purpose-built camera, and eventually receive private textual information through glasses.

This document is intentionally an evolving architecture. Candidate hardware, protocols, manufacturers, physical arrangements, and implementation details should be updated as research progresses.
