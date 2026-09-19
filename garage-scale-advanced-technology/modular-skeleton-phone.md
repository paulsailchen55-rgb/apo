# Modular Skeleton Phone — Physical Architecture Concept

**Date:** 2026-09-18  
**Status:** Preliminary research concept within Garage-Scale Advanced Technology. Not a validated hardware standard.

## Core idea

Imagine a phone whose essential structure is a reusable physical skeleton rather than a sealed slab.

The skeleton provides the mechanical frame, standardized module connections, power distribution, and basic communication/backplane functions. Functional parts are separate modules that can be inserted, removed, replaced, tested, or reconfigured.

The physical interaction is closer to inserting and removing cartridges from a game system or plugging boards into an older personal computer than to opening a modern sealed phone.

The project should not be named after any existing company's prototype or product. The resemblance to other modular-device ideas is part of the context, not the identity of this project.

## Conceptual architecture

```
                 MODULAR PHONE

          ┌─────────────────────────┐
          │   removable display     │
          ├─────────────────────────┤
          │                         │
          │    standardized         │
          │       skeleton          │
          │                         │
          │ [compute] [radio]       │
          │ [storage] [audio]       │
          │ [Wi-Fi]   [sensor]      │
          │ [I/O]     [special]      │
          │                         │
          ├─────────────────────────┤
          │   removable battery     │
          └─────────────────────────┘
```

This drawing is conceptual. It does not establish the electrical, mechanical, thermal, or software standards.

## Module behavior

A module should ideally:

1. fit a standardized physical envelope;
2. slide into the skeleton;
3. mechanically latch;
4. establish a defined electrical connection;
5. identify itself to the system;
6. operate according to a documented interface;
7. be deliberately disconnected;
8. be removable without dismantling the whole phone.

A partially released position could provide a physical disconnected state before complete removal.

That would make the physical state of the module visible and understandable.

## Possible modules

The architecture could eventually accommodate interchangeable:

- displays;
- batteries;
- cellular radios;
- Wi-Fi radios;
- Bluetooth radios;
- compute modules;
- storage modules;
- microphone/audio modules;
- DSP modules;
- cameras;
- environmental sensors;
- accessibility controls;
- specialized scientific sensors;
- security modules;
- external I/O modules.

Not every module needs to be interchangeable with every other module. The standard could define families of compatible slots.

## Standardized physical envelopes

One of the strongest ideas is to standardize dimensions rather than standardize every component's internal design.

For example, a display slot could accept multiple displays with the same physical envelope but different:

- resolution;
- brightness;
- power consumption;
- refresh rate;
- touch capability;
- accessibility characteristics;
- durability.

Similarly, a radio slot could accept different radios while presenting the same defined connection to the rest of the phone.

The key research question is how much interoperability can be gained from physical standardization without creating unreasonable constraints on engineering progress.

## Removable battery

The battery should be independently removable.

The module specification would need to define at least:

- physical dimensions;
- connector;
- voltage range;
- current limits;
- temperature sensing;
- protection requirements;
- charging behavior;
- mechanical retention;
- identification.

Battery modularity must still account for fire, thermal, short-circuit, overcharge, and mechanical safety.

## Physical switches

The skeleton could include actual switches for major subsystems.

Possible examples:

- battery disconnect;
- radio disconnect;
- microphone disconnect;
- camera disconnect;
- sensor disconnect;
- module power switch;
- service/debug state.

The goal is not to eliminate software control.

The goal is to make important physical states independently observable and controllable.

## The module test reader

The phone architecture should have a companion diagnostic reader.

The same removable module that fits the phone could be inserted into a separate test device.

The reader could potentially:

- identify the module;
- check compatibility;
- inspect firmware version;
- test electrical interfaces;
- report health;
- run diagnostics;
- reset supported modules;
- perform authorized recovery;
- verify cryptographic identity;
- detect obvious faults.

This means a suspicious or unknown module could be examined before being installed.

The diagnostic reader becomes a piece of infrastructure rather than a proprietary service appliance.

## Test-before-install workflow

A possible workflow is:

```
obtain module
     ↓
insert into diagnostic reader
     ↓
identify
     ↓
inspect
     ↓
test
     ↓
reset / recover if appropriate
     ↓
verify compatibility
     ↓
install in phone
```

The reader should not automatically assume that every module can be rewritten. Security-sensitive components may require signed firmware, manufacturer authorization, or other controls.

The important point is that the user has a separate physical place to examine the component.

## Module diagnostics as a standard

The phone architecture therefore needs more than a physical connector.

It needs a diagnostic language or protocol.

Possible standardized functions:

- discovery;
- identity;
- capabilities;
- health;
- firmware information;
- error codes;
- self-test;
- recovery;
- secure update;
- calibration status.

An independent diagnostic reader should ideally be able to implement this standard without belonging to one particular phone manufacturer.

## Swappable sensor cases

The case itself is a major modular layer in this architecture.

Instead of making every sensor part of the permanent phone skeleton, the phone could accept different standardized cases. The case would contain the sensors, sensor electronics, and possibly additional power or processing hardware, while the central phone remains the same.

This creates a physical separation between:

**the phone** — the general-purpose communication/computing platform

and

**the case** — the environment-, location-, activity-, accessibility-, or task-specific sensing platform.

The user could therefore own several cases and change them according to where the phone is being used.

For example:

- a home case could contain environmental sensors intended for the home;
- a work case could contain sensors appropriate to a workplace;
- a field case could contain ruggedized or scientific sensors;
- a travel case could emphasize different sensing, power, communications, or physical protection;
- an accessibility case could provide specialized controls or interfaces.

The same phone skeleton would move between them.

Conceptually:

```
                         SAME PHONE

                    ┌───────────────┐
                    │ phone skeleton│
                    └───────┬───────┘
                            │
             ┌──────────────┼──────────────┐
             ↓              ↓              ↓
       HOME CASE        WORK CASE       FIELD CASE
       [sensors]        [sensors]       [sensors]
       [power]          [controls]      [rugged I/O]
       [environment]    [work data]     [science]
```

The case could remain at the location when the person leaves. For example, a home sensing case could stay physically installed or available at home while the phone travels with the user. On returning home, the user could insert the phone into the home case and reconnect to that environment-specific hardware.

This creates an interesting possibility: the phone is portable, while the sensing infrastructure can be location-specific.

A workplace could have its own case. A home could have another. A field station could have another. A laboratory, vehicle, workshop, or other location could have a specialized case.

The case therefore becomes more than a protective shell. It becomes a removable physical sensor platform.

## Case-to-phone interface

For this to work cleanly, the case would need a standardized interface to the phone skeleton.

Possible functions include:

- power delivery;
- sensor data;
- audio;
- high-speed data;
- identification;
- secure authentication;
- case capability reporting;
- firmware update;
- diagnostic access.

The system would need to determine whether the case is merely an accessory, a trusted sensor platform, or a full computing extension.

A useful design principle would be that the phone can recognize a case and report something like:

```
CASE: HOME-ENVIRONMENT
SENSORS: temperature / humidity / air quality / acoustic / other
POWER: external or battery
CAPABILITIES: ...
STATUS: ...
```

The exact sensor list is deliberately left open.

## Location-specific sensing

This architecture creates a different way of thinking about sensors.

Instead of asking:

> How many sensors can we fit inside every phone?

the system asks:

> Which sensors belong with the phone everywhere, and which sensors belong to the places where the phone is used?

A person might not need the same sensing capabilities at home, at work, in a vehicle, outdoors, or in a laboratory.

The physical case becomes a way to carry the appropriate sensing architecture into the situation without permanently burdening the phone with every possible sensor.

This could also make specialized sensors larger, more rugged, better powered, or easier to maintain because they are not constrained by the dimensions of the central phone.

## Persistent place-based hardware

The concept also permits cases to become semi-permanent infrastructure.

A home case could remain connected to home power and maintain environmental sensors while the phone is elsewhere.

When the phone returns, it could physically dock into the case and regain access to those sensors.

A workplace could have its own case.

A field station could have several specialized cases.

This suggests a hybrid architecture:

```
portable computing identity
          +
location-specific physical infrastructure
```

The phone carries the person's general computing and communication environment, while cases can carry the specialized sensing and physical interfaces of particular places.

That distinction is a research concept, not an established device architecture.

## Multiple cases and case inventory

A person could maintain a collection of cases rather than one universal case.

The collection might include:

- home;
- work;
- field;
- travel;
- laboratory;
- workshop;
- vehicle;
- accessibility;
- emergency;
- communications;
- environmental monitoring.

The cases could be standardized enough that the same phone skeleton fits all of them.

A case could also be shared by multiple compatible phones if the architecture supports user/device authentication separately from physical connection.

That raises an important question: should the case belong to the person, the location, the organization, or the phone?

## Sensor cases and the diagnostic reader

The separate diagnostic-reader idea becomes particularly important for sensor cases.

A case or sensor module could be tested independently before it is connected to the phone.

For example:

```
sensor case
     ↓
diagnostic reader
     ↓
identify sensors
     ↓
test sensors
     ↓
check firmware
     ↓
verify calibration/status
     ↓
connect to phone
```

A single diagnostic device might eventually test individual modules as well as complete cases.

This would allow the physical sensing layer to remain inspectable instead of becoming another sealed black box.

## Case security and trust

A sensor case may collect information about its surroundings, so the phone needs to distinguish among:

- a trusted personal case;
- a shared household case;
- an employer-owned case;
- a public or community case;
- an unknown case;
- a modified or compromised case.

The physical connection should not automatically grant unlimited authority.

A case might be permitted to provide sensor measurements while being prohibited from accessing unrelated phone data.

This creates a research question about capability-based permissions at the physical module/case level.

## Sensor privacy

Different cases could also make privacy visible physically.

A home case might contain microphones or environmental sensors that a person does not want active continuously.

Physical switches could provide a direct way to disable individual sensor groups.

The system could also expose the case's sensor inventory physically and in software.

A user should be able to answer:

- What sensors are in this case?
- Which ones are active?
- What are they measuring?
- Where is the data going?
- What is stored locally?
- What is transmitted?
- Who is allowed to access it?

The modular physical architecture does not automatically solve these questions, but it creates a place in the architecture where they can be made explicit.

## Cases as application-specific computers

A sophisticated case could contain its own processor.

For example, a scientific field case might preprocess sensor data before sending it to the phone.

A home environmental case might continuously monitor sensors while the phone is absent and synchronize measurements when the phone returns.

A workplace case might have specialized instruments that the phone uses as a display and communication interface.

This means the case could range from:

**passive shell → sensor board → intelligent sensor platform → specialized computer**

The phone skeleton remains the common platform.

## Case exchange as physical configuration

The user should be able to change the phone's capabilities physically:

```
leave home
   ↓
remove home case
   ↓
install travel/work/field case
   ↓
phone recognizes new capabilities
   ↓
use phone
   ↓
return home
   ↓
install home case
   ↓
home capabilities return
```

This is the modular configuration principle extended from internal cards to the entire exterior of the phone.

It could make the physical configuration of a computing system visible in a way that software-only configuration does not.

## Serviceability

A modular phone should make the service path explicit:

```
symptom
  ↓
identify suspected module
  ↓
remove module
  ↓
test separately
  ↓
repair / replace
  ↓
retest
  ↓
reinstall
```

This is different from diagnosing an entire sealed phone as one indivisible object.

The architecture could support independent repair shops, schools, libraries, community workshops, and individual experimenters.

## Security questions

Modularity creates new security questions.

A system must distinguish among:

- a genuine module;
- a compatible third-party module;
- a modified module;
- a damaged module;
- a counterfeit module;
- a compromised module.

The diagnostic reader could help establish module identity and status, but the security architecture should not rely on physical appearance alone.

Possible mechanisms include:

- cryptographic module identity;
- signed firmware;
- secure boot;
- capability declarations;
- hardware attestation where appropriate;
- explicit user approval for unknown modules;
- revocation mechanisms.

These mechanisms should be designed so that security does not automatically become a justification for making the hardware opaque or non-repairable.

## Physical transparency versus software transparency

The concept intentionally has two kinds of inspectability.

Physical inspectability means the user can see and remove the modules.

Software/system inspectability means the user can understand what the modules report, how they communicate, and what diagnostic tools can observe.

A physically modular phone with completely closed diagnostic protocols would preserve only part of the desired agency.

## Research questions

1. What physical dimensions could realistically become a long-lived module standard?
2. What connector system could survive thousands of insertion/removal cycles?
3. How should mechanical retention work?
4. How should a module indicate that it is disconnected?
5. What power architecture would allow safe module removal while the phone remains partly operational?
6. Which modules need hot-swap capability and which should require shutdown?
7. How could displays be standardized physically while allowing radically different technologies?
8. How could radio modules be replaced without making regulatory certification impossible?
9. What should the diagnostic reader physically look like?
10. Could one reader support modules from many manufacturers?
11. What parts of the diagnostic protocol should be public?
12. How could a user distinguish a counterfeit module from a genuine but modified one?
13. How can secure boot coexist with independent repair?
14. How can modules be tested before installation?
15. How can failed modules be repaired rather than discarded?
16. What would a small workshop need to manufacture replacement modules?
17. Which module types are realistic for local manufacturing and which remain industrial-only?
18. How small can the modules become before modularity loses practical value?
19. Can a common physical envelope survive multiple generations of technology?
20. How should accessibility modules be represented in the system?
21. Could libraries or community laboratories maintain inventories of modules and diagnostic readers?
22. What would a genuinely open module ecosystem require from manufacturers?
23. What economic arrangements could support manufacturers while preserving public experimentation?
24. What lessons from older modular PCs and cartridge-based machines transfer to modern mobile computing?
25. Which lessons fail because of modern power density, radio regulation, battery safety, semiconductor fabrication, or thermal constraints?
26. What should be part of the permanent phone skeleton, and what should be moved into interchangeable cases?
27. Which sensors are useful everywhere, and which are better attached to a home, workplace, vehicle, field station, or other location?
28. Can a home case operate as a persistent environmental-sensing station while the phone is away?
29. How should a phone authenticate and trust a case that belongs to a location rather than to the phone owner?
30. Can one standardized case interface support passive sensors, powered sensors, intelligent sensor platforms, and specialized computers?
31. What physical dimensions and connector arrangements would make cases interchangeable across generations of phone skeletons?
32. How should power be shared between a phone and a case?
33. Should a case be able to operate independently when the phone is absent?
34. How should sensor data be stored when the phone is away and synchronized when it returns?
35. How should physical switches on a case control microphones, cameras, radios, or other sensors?
36. Can the diagnostic reader test a complete case as well as individual modules?
37. How can calibration status and sensor provenance be represented and independently checked?
38. How can location-specific cases preserve privacy when they contain environmental or workplace sensors?
39. Could a case be shared among multiple compatible phones without confusing identity, authorization, or ownership?
40. What case types would be useful enough to justify maintaining a physical inventory?
41. Could libraries, workplaces, community laboratories, or households maintain shared case inventories?
42. What happens when a case is deliberately left at home, but the phone's owner needs its sensor data remotely?
43. Which functions should remain available through the phone when the case is absent?
44. Could the same phone skeleton support radically different cases without becoming too complex to configure safely?

## Relation to the Simple Voice Link prototype

The current Simple Voice Link recorder-in-case experiment can be viewed as a transitional form.

Today:

```
phone + external recorder + microphone + battery + wiring
```

Possible future:

```
phone skeleton + standardized audio/DSP module
```

A further extension is:

```
phone skeleton
      +
interchangeable sensor/audio case
      +
standardized internal modules
```

The second architecture could allow the audio-processing function to be removed, tested separately, upgraded, or replaced without replacing the whole phone.

The case architecture could also allow a Simple Voice Link microphone/audio system to be one specialized case among many rather than permanently defining the phone.

This is one reason the modular phone belongs in the broader manufacturing research folder rather than being buried inside the audio project.

## Status

This is a physical architecture concept, not a claim that all of these modules or cases can currently be standardized at one practical size.

The central experiment is to investigate whether modern phone functionality can be reorganized into a visible, removable, testable module system while retaining modern performance, safety, security, communications, and location-specific sensing capabilities.
