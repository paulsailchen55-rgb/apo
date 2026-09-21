# Intellectual Property Clocks

A computing product does not necessarily have one legal clock attached to it.

A single device can contain hardware, software, firmware, components, communications systems, designs, standards, and services that are governed by different legal and commercial timelines. A patent may have one term. A component may be covered by another patent. Software may carry copyright and license conditions. A trademark may have renewal requirements. A service may have a support period. A radio may be subject to regulatory and geographic restrictions.

The result is that an ordinary person looking at one physical object may be looking at many overlapping clocks.

## The problem

The **Open Market Computing Products** concept proposes a parallel market category in which at least some computing products are deliberately designed to give owners meaningful freedom to repair, study, modify, develop, and experiment.

For that category to be useful, however, openness cannot be described only as a philosophical principle. The boundaries around a particular product need to be understandable.

A person should be able to ask:

- What can I legally repair?
- What can I modify?
- What software can I replace?
- What firmware can I study or replace?
- Which components remain subject to third-party rights?
- Which restrictions apply only in a particular country?
- Which rights are active now?
- Which rights expire?
- Which rights require renewal or maintenance?
- When does a restriction change?
- What happens when a component, license, patent, or service reaches the end of its term?

The purpose of an intellectual-property clock system would not be to erase intellectual property. It would be to make the temporal boundaries surrounding an object visible.

## Different clocks can coexist

A device may have, among other things:

- patent priority and filing dates;
- patent expiration dates;
- patent maintenance-fee deadlines;
- continuation or divisional applications;
- copyright terms;
- trademark registration and renewal dates;
- software-license terms;
- open-source license obligations;
- third-party component licenses;
- standards-related licensing conditions;
- carrier or communications agreements;
- regulatory certifications;
- litigation or injunction periods;
- export-control or trade restrictions;
- manufacturer support and end-of-support dates;
- security-update availability;
- replacement-parts availability.

These are not necessarily the same kind of legal right, and they do not necessarily expire at the same time. Some may also be jurisdiction-specific.

## A clock map for a device

A possible future standard could represent a product approximately like this:

```
DEVICE
├── Hardware
│   ├── component A → patent clock
│   ├── component B → patent clock
│   ├── component C → license clock
│   └── mechanical design → IP clock
├── Software
│   ├── operating system → license/copyright clock
│   ├── driver → license/IP status
│   ├── library → open-source license
│   └── proprietary component → restrictions
├── Communications
│   ├── radio certification
│   ├── carrier restrictions
│   └── national regulations
├── Geography
│   ├── United States
│   ├── European Union
│   ├── Japan
│   └── other jurisdictions
└── TIME
    ├── active now
    ├── expires
    ├── renews
    ├── becomes unrestricted
    └── requires action
```

The map should distinguish **legal rights** from **commercial policies** and from **technical limitations**. An end-of-support date, for example, is not necessarily the same thing as an expiration of intellectual property.

## Human-readable status

A future open computing product could provide a plain-language status panel such as:

> **DEVICE OPENNESS STATUS**
>
> Hardware modification: Permitted under stated conditions  
> Repair: Permitted under stated conditions  
> Firmware replacement: Permitted under stated conditions  
> Sensor access: Available  
> Software development: Available  
> Commercial redistribution: See applicable licenses  
> Radio modification: Restricted  
> Third-party component rights: Component-specific  
> Jurisdiction: United States  
> Important dates: See clock map

The exact legal conclusions would still require appropriate legal authority and jurisdiction-specific analysis. The purpose is to prevent the ordinary user from having to reconstruct the entire legal structure from scattered documents.

## Temporal accountability

This leads to a broader concept: **temporal accountability**.

A product should have a discoverable record of the important dates that determine its openness and restrictions.

The record could show:

1. when a right or restriction began;
2. what object or component it applies to;
3. who holds or administers the relevant right;
4. which jurisdiction it applies in;
5. whether it is currently active;
6. whether it can be renewed, extended, continued, or otherwise changed;
7. when the next relevant event occurs;
8. what changes when that event occurs;
9. what evidence supports the recorded status.

This could become a machine-readable as well as human-readable standard.

## The "one day of experimentation" problem

One motivation for this concept is simple:

**A person should be able to know when they can legitimately experiment with an object.**

That person might be a child, student, independent developer, researcher, artist, repairer, teacher, hobbyist, or ordinary adult with no corporate resources.

Large companies can employ lawyers, engineers, compliance departments, and licensing specialists. An individual experimenting alone does not have the same infrastructure.

The proposal is not that individuals should be exempt from intellectual-property law. Rather, it asks whether the boundaries of lawful experimentation can be made sufficiently legible that a person does not need an institutional legal department simply to understand the basic status of the machine in front of them.

A possible future product might therefore expose an explicit **experimentation boundary**:

- what is clearly permitted;
- what is permitted only under a license;
- what is technically possible but legally restricted;
- what is jurisdiction-dependent;
- what is uncertain and requires professional advice;
- what becomes available after a documented date.

The goal is not to create a promise that every action is lawful. The goal is to make the boundary visible.

## International complexity

Intellectual-property rights are territorial. A product may therefore have different legal states in different countries.

International filing systems and treaties can simplify the process of seeking protection across countries, but national and regional laws still matter. A single global countdown should therefore not be assumed.

A useful system would preserve the jurisdictional distinction rather than hide it.

For example:

```
DEVICE X

United States
  Patent A → active until [date/status]
  Patent B → [status]
  License C → [conditions]

European Union
  Patent A → [status]
  Patent B → [status]
  License C → [conditions]

Japan
  Patent A → [status]
  Patent B → [status]
  License C → [conditions]
```

The dates and legal statuses would need to be supplied from authoritative records rather than inferred.

## Relationship to the parallel-market proposal

This concept strengthens the **Open Market Computing Products** proposal.

A parallel market category needs a boundary that people can actually see.

If an officially supported open product says that owners can modify it, but the user cannot determine which parts of the machine remain restricted, then the openness is difficult to exercise in practice.

The proposed clock map therefore becomes part of the product itself:

**Open product + visible legal/technical boundary + temporal status = an actionable platform for experimentation.**

This is not intended to replace legal advice or eliminate complexity. It is an attempt to keep complexity from becoming invisible.

## Research questions

- Can a standardized "legal clock map" be created for a computing product?
- Which dates can be represented reliably from public records?
- How should component-level patent rights be associated with a physical product?
- How should copyright, patent, trademark, licensing, and regulatory timelines be distinguished?
- How should the system represent jurisdiction-specific differences?
- How should uncertainty be displayed?
- Could manufacturers publish machine-readable openness metadata?
- Could an independent organization verify and timestamp these records?
- Could an owner see the relevant status without understanding patent law?
- How should expiration, renewal, continuation, and litigation events update the record?
- Could the same framework apply to vehicles, appliances, scientific instruments, or other complex physical products?
- What would a genuinely useful "experimentation boundary" look like for an individual?

## Working principle

> **If a machine has many clocks around it, the person using the machine should not have to discover those clocks by accidentally crossing their boundaries.**

The objective is not to abolish intellectual property.

The objective is to make the temporal and jurisdictional structure surrounding a technological object visible enough that ownership, repair, study, modification, and experimentation can be understood in ordinary human terms.
