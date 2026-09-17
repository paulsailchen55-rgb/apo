# The People's Relay — Concept

## Status

**Concept / possibility / working design.** This document does not describe a deployed network, finished product, incorporated organization, or established technical implementation.

## Working identity

**The People's Relay**

Possible working line:

> **Keep Democracy Weird.**

The concept is intentionally broader than any one country or institution. It is a possible public-interest communications utility centered on individual agency, privacy by construction, and reliable delivery.

## Purpose

The working purpose is to help an individual communicate a legitimate message without requiring the person to become an institution merely to use ordinary communications infrastructure.

The system could eventually support combinations of:

- personal/private email
- scheduled correspondence
- group communications
- SMS or other messaging channels
- physical mail
- multilingual communication
- accessibility support
- AI-assisted drafting, translation, organization, and research
- delivery-status reporting

These are possibilities, not commitments or claims that the services currently exist in the proposed form.

## Core principle

> **The purpose of the Relay is not to give people power over other people. It is to give people power over their own ability to communicate.**

A related boundary:

> **The AI may write it. The Relay may carry it. Only you may send it.**

Or, more formally:

> **AI can prepare anything. AI cannot publish anything.**

## Human authorization boundary

The final transmission step is intended to remain a human-controlled security boundary.

A possible flow:

1. Local AI helps prepare a message.
2. A privacy gateway identifies information that actually needs to leave the device.
3. The user can inspect the outbound representation.
4. The user initiates final authorization.
5. Hardware-backed user presence and deliberate interaction may be required.
6. The authorized transport sends the message.
7. The system reports what it can verify.

Fingerprint, PIN/passkey, trusted hardware, and sensor signals are possible components. Sensors alone should not be treated as proof that a human is present; the engineering goal is deliberate, hardware-backed authorization.

## Local brain + larger brain

One proposed architecture is:

**Device → local AI → Privacy Gateway → authorized external assistance → response → local integration**

The local model could handle composing, reasoning, translation, summarization, classification, and other tasks where local processing is sufficient.

External AI could be used when the user explicitly authorizes it or when a defined policy permits a particular low-risk task.

A privacy gateway could minimize unnecessary context and remove or transform identifying information before an external request is made.

Important limitation: sanitization or encryption cannot honestly be described as a guarantee that an external provider retains nothing or that communications are impossible to correlate. Provider policies and network-level metadata still matter.

## Permission levels

A possible model:

- **Level 0 — Local only:** no external network assistance.
- **Level 1 — Approved assistance:** user authorizes a defined external task.
- **Level 2 — Sanitized assistance:** only minimized or transformed context leaves the device.
- **Level 3 — Sensitive material:** local-only processing.

These are design concepts for investigation, not a completed security specification.

## Modularity

The local AI layer should not be permanently tied to one model family. The architecture should allow replaceable open-weight or otherwise locally runnable models, subject to hardware, licensing, performance, and security constraints.

The communications stack should similarly prefer mature, independently reviewed protocols and implementations rather than inventing new cryptography.

## Delivery truth

The Relay should distinguish the stages of communication rather than treating a button press as proof of delivery:

**Prepared → Authorized → Accepted → Queued → Transmitted → Acknowledged**

If a stage cannot be confirmed, the system should communicate that uncertainty.

> **A communication system should not silently turn transmission into uncertainty.**

This does not mean the Relay can make communication impossible to disrupt. It means the system should make failures observable where technically possible and provide recovery paths rather than fabricating certainty.

## Self-representation

A person should not need to become an institution in order to exercise ordinary technological or civic agency. Institutional affiliation may be relevant when genuinely necessary for a particular purpose. Where an individual can legitimately perform an activity on their own behalf, the system should not manufacture an institutional requirement merely because its infrastructure was designed around organizations.

Practical test:

> **Can an individual accomplish the legitimate purpose without creating an organization? If yes, the system should allow it.**

## Communication without extraction

The Relay should be designed around the question:

> **What information is actually necessary to accomplish this communication?**

Possible defaults include local storage, minimal data collection, no unnecessary tracking, no unnecessary accounts, open standards, inspectable source, documented dependencies, reproducible builds where practical, and independent/community review.

The objective is not to claim that all infrastructure can be free or costless. A sustainable system still has real resource requirements. The design goal is to avoid making the people using the system themselves into an unnecessarily extracted resource.

## Collective communications without an autonomous cannon

A major threat-model boundary is the difference between **many people exercising individual communication** and **an automated system directing mass influence**.

A future Relay could potentially help many individuals submit the same legitimate concern or aggregate independently authorized support. It should not be designed as an autonomous mechanism for mass targeting, retaliation, harassment, endless retries, or escalating pressure.

Possible aggregation pattern:

> **5,183 people independently submitted this concern.**

That is conceptually different from an AI autonomously generating and firing 5,183 targeted messages.

## Explicit non-goals / boundaries

The concept should not intentionally include:

- autonomous mass targeting
- autonomous retaliation
- autonomous escalation
- dead-man publication mechanisms
- hidden delayed-release mechanisms
- “keep trying forever” delivery logic
- secret administrator impersonation
- a universal master key
- a single hidden command center with total visibility
- autonomous identification of new targets for political or commercial pressure
- mechanisms whose primary purpose is to evade accountability rather than protect legitimate privacy

These boundaries are design proposals and should be revisited through threat modeling and security review.

## Decentralization and capture resistance

The objective should not be an unrealistic promise that governments, corporations, or other actors can never interfere with the system. A more defensible goal is **compartmentalization**:

> **No single party should possess unnecessary unilateral control over the whole communications picture.**

Possible properties include multiple relay operators, compartmentalized services, least privilege, hardware-backed keys, open source, reproducible builds, documented dependencies, independent review, and rapid patching.

A compromised component should reveal as little as practical rather than automatically compromising every other component.

## The early-computing lesson

The originating discussion includes a firsthand recollection of early public-library computers and Internet Explorer-era deployments in which unexpected web behavior could overwhelm or crash systems and lead to IT intervention. The recollection is retained as experience, not treated as a complete historical account.

The resulting engineering principle is:

> **Users will surprise you. Attackers will surprise you. Software will surprise you. Institutions will surprise you. Design for surprise.**

## Development philosophy

> **Dream weird. Verify everything.**

And:

> **Radical about human agency; conservative about irreversible power.**

The project should prefer reversible experiments, explicit permissions, test environments, narrow capabilities, clear failure states, and human review before consequential actions.

## Possible future reference device

A possible edge-AI reference device would need to be evaluated for:

- strong on-device AI acceleration
- sufficient RAM
- hardware-backed security
- biometric/PIN/passkey support
- accelerometer/gyroscope and other useful sensors
- secure boot
- long security-support window
- developer APIs
- encrypted communications
- ability to run user-controlled software
- where possible, an unlockable bootloader or independently supported OS

Hardware should be selected only after requirements are tested. A prototype should not require immediately purchasing an expensive flagship device.

## Not a guarantee

No architecture can honestly guarantee perfect anonymity, permanent availability, immunity from surveillance, or immunity from shutdown. The purpose of the design is to reduce unnecessary centralization, reduce unnecessary data exposure, preserve user agency, and make failure and uncertainty more visible.
