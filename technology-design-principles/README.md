# Technology Design Principles

A growing, reusable collection of design principles for technology that prioritizes user control, repairability, privacy, physical agency, and open-ended use.

This section is intended as a shared reference rather than a finished doctrine. Principles can be added, refined, challenged, tested, or removed as evidence develops.

## User-Controllable Connectivity

### Wireless should be a capability, not an unavoidable property

Where practical, a device should be fully usable without an embedded wireless connection. Wireless capability should be something the user can add, enable, disable, replace, or physically disconnect.

Preferred pattern:

**device → wired operation → optional wireless module**

rather than:

**device → permanently embedded radio → software-controlled connectivity**

### Design principles

- **Physical radio disconnect:** Provide a real switch, removable module, or equivalent physical means of disconnecting the radio where practical.
- **Wired-first operation:** Core functions should remain available without Bluetooth, Wi-Fi, cellular, or cloud connectivity when the device does not inherently require communications.
- **Radio power control:** Where technically and legally feasible, expose meaningful user control over transmission power rather than fixing it at a level higher than necessary.
- **Range control:** Allow users to minimize the physical coverage of a transmission where the technology permits it.
- **Time control:** Give users meaningful control over when a radio may operate.
- **Transmission control:** Prevent automatic/background communications when the user has chosen not to transmit.
- **Local operation:** Ordinary use should not require a cloud account when local operation is technically feasible.
- **Upgradeable wireless:** Prefer removable or replaceable connectivity modules over permanently embedded radios.
- **Repairability:** Wireless components should be independently replaceable where practical.
- **Visible state:** Users should be able to determine whether a radio is actually disconnected, rather than having to trust a software indicator alone.

### Design question

> **Can a person own a device without having to surrender control of its communications?**

This is an initial section. It is deliberately open for expansion as other technologies, standards, laws, and user experiences are examined.

## Evidence discipline

Future entries should distinguish:

- **KNOWN** — documented fact or established specification
- **CALCULATED** — derived from known information
- **TESTED** — personally or independently tested
- **PROPOSED** — design proposal
- **SPECULATIVE** — possibility requiring investigation
- **UNKNOWN** — information not yet established

The goal is not to reject wireless technology. The goal is to make connectivity **user-selectable, understandable, physically controllable, and removable whenever practical**.
