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

## Replaceable Power

### A dead battery should not make a healthy device disposable

Where the technology and safety requirements permit, batteries should be designed to be **replaceable by the owner or an ordinary repair provider**.

A battery is a consumable component. If the battery reaches the end of its useful life while the rest of the device remains functional, replacing the battery should restore the useful life of the device rather than forcing disposal or replacement of the entire product.

The same principle applies to other power components where practical, including power supplies, charging modules, connectors, and related serviceable components.

### Design principles

- **Replaceable battery:** The battery should be removable and replaceable without destructive disassembly where practical.
- **Standardized access:** Battery access should use ordinary, clearly documented procedures.
- **Safe replacement:** Safety-critical batteries should still have appropriate protection against incorrect installation, short circuits, thermal events, and other hazards.
- **Replacement availability:** Manufacturers should make compatible replacement batteries available for a meaningful portion of the device's expected service life.
- **No unnecessary lock-in:** Battery replacement should not require an unnecessary subscription, proprietary service relationship, or software authorization when there is no legitimate safety or technical reason.
- **Power-module repairability:** Power supplies and charging components should be independently replaceable when feasible.
- **Documentation:** The owner or repair provider should be able to identify the correct replacement part and procedure.

### Design question

> **If the battery dies before the device does, why should the device die with it?**

## Modular Field Replacement

### A device should be repairable by replacing modules, not rebuilding the machine

A strong repair architecture treats common failure points as **field-replaceable modules**.

The user described professional audio equipment from companies such as Crest and Peavey as an important practical reference: replacement components could be kept available, sometimes purchased in quantity, and exchanged when a component failed rather than requiring an entire system to be discarded or sent away for complex repair.

The principle can extend far beyond audio equipment.

**detect failure → remove module → insert replacement → test → return to service**

The objective is not that every component must be user-replaceable. The objective is that predictable failure points should be designed around practical replacement wherever feasible.

### Design principles

- **Modular architecture:** Divide a device into serviceable functional modules.
- **Field replacement:** Common failures should be repairable where the device is being used, when safety permits.
- **Parts availability:** Replacement modules should remain obtainable throughout the intended service life.
- **Bulk availability:** Organizations, caregivers, repair shops, and users should be able to keep spare modules on hand.
- **Independent replacement:** A failed subsystem should not require replacement of unrelated functioning subsystems.
- **Functional testing:** A replacement module should have a straightforward way to verify that it works.
- **Documentation:** Service procedures should identify modules, failure symptoms, replacement steps, and required tools.
- **No artificial lockout:** A legitimate replacement should not be rejected merely because it was not installed by an authorized service provider, unless a documented safety requirement genuinely requires authorization.

### Accessibility and assistive technology

This principle becomes especially important for devices that a person **cannot simply live without**, including wheelchairs, mobility equipment, communication devices, hearing-related equipment, adaptive controls, and other assistive technologies.

A person who depends on a device should not be placed in a situation where a small failed component turns into an extended loss of mobility, communication, independence, or access.

Repairability is therefore not merely a consumer convenience. In assistive technology, it can be part of preserving **continuity of human agency**.

## Minimal-Tool Repair

### The device should contain or clearly specify the means of opening and servicing it

A repairable design should minimize specialized tooling.

A strong target is:

**one common tool → access the major serviceable modules → replace the failed part → reassemble**

This does not mean every device literally needs one tool. Safety, sealing, electrical isolation, torque requirements, and other engineering constraints may require additional tools. The principle is to avoid unnecessary tool diversity and proprietary barriers.

### Integrated tool concept

The user's proposed example is a device that **contains its own basic service tool**.

For example, a phone could have a pen-like accessory that slides into the device and serves not only as a writing/input tool but also as the basic tool for opening the device and replacing its intended service modules.

The broader principle is:

> **If a device expects to be maintained, the means of maintaining it should be part of the design.**

Possible implementations include:

- a removable stylus that doubles as a service tool
- a captive screwdriver or driver bit
- a tool stored in the battery compartment
- a standardized fastener that can be operated by the device's included accessory
- a clearly identified common tool that users can obtain almost anywhere

### Design question

> **Can the owner repair the device with the minimum practical number of tools, without requiring a proprietary workshop?**

## Continuity of Ownership

These principles share a larger objective:

**A device should remain useful after its first component fails.**

The intended ownership cycle is not:

**buy → use → component fails → discard → buy again**

but:

**buy → use → maintain → replace component → repair → continue using → upgrade individual modules when appropriate**

This matters particularly for people with limited financial resources, people who depend on assistive equipment, community organizations operating on tight budgets, and anyone who would rather maintain a functioning device than repeatedly replace an entire product.

The principle is not “never replace a device.” Sometimes replacement is appropriate. The principle is that **a manufacturer should not make replacement of the entire device the default consequence of a replaceable component reaching the end of its service life.**

## Evidence discipline

Future entries should distinguish:

- **KNOWN** — documented fact or established specification
- **CALCULATED** — derived from known information
- **TESTED** — personally or independently tested
- **PROPOSED** — design proposal
- **SPECULATIVE** — possibility requiring investigation
- **UNKNOWN** — information not yet established

The goal is not to reject wireless technology, integrated batteries, or proprietary engineering categorically. The goal is to establish a design vocabulary for **user control, repairability, modular replacement, continuity of ownership, and practical long-term use**.
