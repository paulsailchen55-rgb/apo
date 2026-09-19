# Modular Skeleton Phone — Physical Architecture Concept

**Date:** 2026-09-18  
**Status:** Expanded research concept within Garage-Scale Advanced Technology. Not a validated hardware standard.

## Core idea

Imagine a phone whose essential structure is a reusable physical skeleton rather than a sealed slab.

The skeleton provides the mechanical frame, standardized module connections, power distribution, and basic communication/backplane functions. Functional parts are separate modules that can be inserted, removed, replaced, tested, or reconfigured.

The physical interaction is closer to inserting and removing cartridges from a game system or plugging boards into an older personal computer than to opening a modern sealed phone.

A central feature of this architecture is that **the phone's case is itself a modular technological layer**.

The phone can operate as a phone and computer without a specialized case. A case is then something the user puts onto the phone to give it additional, environment-specific abilities. The case is therefore analogous to a technological skin: removable, replaceable, configurable, testable, and potentially highly instrumented.

The project should not be named after any existing company's prototype or product. The resemblance to other modular-device ideas is part of the context, not the identity of this project.

## Two systems that fold together

The architecture is easiest to understand as two modular systems that can be used together without being dependent on each other.

**System 1 — the skeleton**

The portable phone skeleton contains the general-purpose computing and communications functions.

It can have interchangeable:

- compute modules;
- memory/RAM;
- storage;
- cellular radio;
- Wi-Fi/radio modules;
- audio/DSP;
- display;
- battery;
- I/O;
- security modules;
- other internal functions.

The exact division between these modules is a research question.

**System 2 — the skin/case**

The removable case provides additional sensing, controls, physical interfaces, power, protection, and potentially local computation.

A user can operate the skeleton without the case.

Putting on a particular case changes what the phone can sense or do in that environment.

This means the case is not merely an accessory or protective cover. It is a **configurable sensor and capability platform**.

Conceptually:

```
              PHONE SKELETON
        general-purpose portable core
                    │
             standardized case
                    │
          ┌─────────┼─────────┐
          ↓         ↓         ↓
       HOME       WORK       FIELD
        SKIN       SKIN       SKIN
       sensors    sensors    sensors
       controls   tools      science
       power      I/O       ruggedization
```

The two systems can be developed independently and then combined.

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
          │ [Wi-Fi]   [memory]      │
          │ [I/O]     [security]    │
          │                         │
          ├─────────────────────────┤
          │   removable battery     │
          └───────────┬─────────────┘
                      │
              CASE / SENSOR SKIN
        ┌─────────────┴─────────────┐
        │ sensors / power / controls│
        │ instruments / I/O / DSP   │
        │ optional local computing  │
        └───────────────────────────┘
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

## Possible internal modules

The skeleton could eventually accommodate interchangeable:

- displays;
- batteries;
- cellular radios;
- Wi-Fi radios;
- Bluetooth radios;
- compute modules;
- RAM/memory modules;
- storage modules;
- microphone/audio modules;
- DSP modules;
- cameras;
- security modules;
- external I/O modules;
- specialized internal sensors;
- accessibility controls.

Not every module needs to be interchangeable with every other module. The standard could define families of compatible slots.

## The case as a technological skin

The most important extension of the concept is to treat the phone case as a second modular architecture rather than as a passive enclosure.

The case can contain a configurable array of sensors chosen for a particular environment or job.

A case might include:

- environmental sensors;
- radiation sensing, such as a miniaturized Geiger-counter-type instrument;
- temperature and humidity;
- air-quality and chemical sensing;
- particulate measurement;
- acoustic and ultrasonic sensing;
- light and optical sensing;
- magnetic/electromagnetic sensing;
- vibration and motion sensing;
- pressure and altitude;
- soil or water measurements;
- specialized biological or physiological sensing where appropriate;
- cameras or optical instruments where desired;
- specialized scientific instruments;
- physical controls;
- additional battery capacity;
- communications interfaces;
- local processing.

This is an intentionally broad research inventory. The presence of a category here does not establish that a particular sensor can be safely or accurately miniaturized into a phone case.

The design principle is:

> **Instead of putting every possible sensor inside every phone, put the appropriate sensor array into the skin for the situation in which the phone is being used.**

## A family of sensor skins

Different people and occupations could use the same phone skeleton with radically different cases.

### Home/environmental skin

A home case could monitor things such as:

- temperature;
- humidity;
- air quality;
- particulate matter;
- sound;
- vibration;
- light;
- radiation;
- other household environmental variables.

It could be designed around home environmental measurement rather than general-purpose portability.

### Workplace/inspection skin

An inspector or worker could use a case containing the instruments relevant to a particular workplace.

The exact array could vary by occupation and regulatory requirements.

The important idea is that the phone becomes a portable instrument platform rather than requiring a completely separate proprietary instrument for every task.

### Field/scientific skin

A field worker could install a rugged case containing sensors appropriate to:

- geology;
- archaeology;
- oceanography;
- hydrology;
- environmental science;
- ecological monitoring;
- atmospheric measurements;
- soil measurements;
- water measurements;
- other field research.

The case could provide larger or more specialized sensors than would be practical to permanently build into the phone skeleton.

### Laboratory skin

A laboratory case could emphasize:

- measurement;
- controlled sensor interfaces;
- calibration;
- data logging;
- specialized instruments;
- external connections;
- local processing.

### Vehicle/industrial skin

A case could be designed around:

- vibration;
- temperature;
- pressure;
- machinery monitoring;
- vehicle interfaces;
- specialized communications;
- inspection equipment.

### Accessibility/communication skin

A case could provide:

- specialized physical controls;
- alternative input devices;
- audio hardware;
- tactile interfaces;
- switches;
- microphones;
- speakers;
- communication accessories.

The Simple Voice Link audio system could eventually be one specialized skin rather than a permanent characteristic of every phone.

## The case can be an instrument kit

The user does not necessarily carry only one universal sensor case.

The cases themselves could be part of a kit.

For example:

```
PERSON
  │
  ├── phone skeleton
  │
  ├── home sensor skin
  ├── work/inspection skin
  ├── field geology skin
  ├── ocean/environment skin
  ├── laboratory skin
  └── accessibility/communication skin
```

Each case could be physically maintained, repaired, calibrated, and tested as an instrument.

The person would therefore carry not just a phone but a collection of configurable technological tools that all use the same central computing/communications skeleton.

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
- diagnostic access;
- synchronization of locally stored measurements.

A case could identify itself and report something like:

```
CASE: FIELD-OCEAN-ENVIRONMENT
SENSORS:
  temperature
  pressure
  conductivity
  acoustic
  optical
  other
POWER: battery / external
PROCESSING: local / phone / hybrid
DATA: local storage + synchronization
STATUS: ...
CALIBRATION: ...
```

The exact sensor list is deliberately open.

## Location-specific sensing

This architecture creates a different way of thinking about sensors.

Instead of asking:

> How many sensors can we fit inside every phone?

the system asks:

> Which sensors belong with the phone everywhere, and which sensors belong to the places where the phone is used?

A person might not need the same sensing capabilities at home, at work, in a vehicle, outdoors, in a laboratory, or in a field environment.

The physical case becomes a way to bring the appropriate sensing architecture into the situation without permanently burdening the phone with every possible sensor.

This could also make specialized sensors larger, more rugged, better powered, or easier to maintain because they are not constrained by the dimensions of the central phone.

## Persistent place-based sensor infrastructure

A case does not necessarily have to travel with the phone.

A home case could remain at home, connected to power, and continue monitoring its environment while the phone is being used elsewhere.

A workplace case could remain at the workplace.

A field station could maintain specialized cases.

When the user returns, the phone could be inserted into the case and reconnect to its sensors and stored measurements.

Conceptually:

```
PORTABLE PHONE SKELETON
          +
LOCATION-SPECIFIC SENSOR INFRASTRUCTURE
```

This creates a hybrid architecture in which the person's portable computing identity and the physical sensing infrastructure of a place are separate but interoperable.

## Cases as configurable instruments

A case can range from a simple accessory to a sophisticated independent instrument:

```
protective shell
      ↓
sensor board
      ↓
multi-sensor platform
      ↓
intelligent sensor platform
      ↓
specialized scientific / inspection computer
```

A sophisticated case could contain its own processor and preprocess data before passing measurements to the phone.

A home case could continue collecting measurements without the phone.

A field case could perform local calculations so that the phone does not have to process every raw sensor stream.

The phone skeleton remains the common computing and communications platform.

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
- detect obvious faults;
- inspect calibration status.

This means a suspicious, unknown, repaired, or newly purchased module could be examined before being installed.

The diagnostic reader becomes a piece of infrastructure rather than a proprietary service appliance.

## Sensor-case test reader

The same concept should apply to complete cases.

A sensor case could be removed from the phone and tested independently.

```
SENSOR CASE
     ↓
DIAGNOSTIC READER
     ↓
identify case
     ↓
identify sensor inventory
     ↓
test each sensor
     ↓
check firmware
     ↓
check calibration/status
     ↓
verify interfaces
     ↓
approve for use
```

The reader might eventually test:

- whether each sensor responds;
- whether the expected sensors are physically present;
- firmware versions;
- calibration records;
- battery and power behavior;
- communication interfaces;
- obvious faults;
- data formats;
- security identity;
- environmental operating limits.

A complete case could therefore be treated like a scientific instrument that can be checked before deployment.

## Test-before-install workflow

A possible workflow is:

```
obtain module or case
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
verify compatibility and calibration
       ↓
install
       ↓
phone reports available capabilities
```

The reader should not automatically assume that every module can be rewritten. Security-sensitive components may require signed firmware, manufacturer authorization, or other controls.

The important point is that the user has a separate physical place to examine the component.

## Module and case diagnostics as a standard

The architecture therefore needs more than physical connectors.

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
- calibration status;
- sensor inventory;
- measurement status;
- provenance.

An independent diagnostic reader should ideally be able to implement this standard without belonging to one particular phone manufacturer.

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

The skeleton and cases could include actual switches for major subsystems.

Possible examples:

- battery disconnect;
- radio disconnect;
- microphone disconnect;
- camera disconnect;
- sensor-group disconnect;
- case power switch;
- module power switch;
- service/debug state.

The goal is not to eliminate software control.

The goal is to make important physical states independently observable and controllable.

For sensor-heavy cases, a visible physical switch could make it clear that a particular sensing group is off rather than requiring the user to trust a software indicator alone.

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

Different cases could make privacy visible physically.

A home case might contain microphones or environmental sensors that a person does not want active continuously.

Physical switches could provide a direct way to disable individual sensor groups.

The system could expose the case's sensor inventory physically and in software.

A user should be able to answer:

- What sensors are in this case?
- Which ones are active?
- What are they measuring?
- Where is the data going?
- What is stored locally?
- What is transmitted?
- Who is allowed to access it?
- What happens to the data when the case is left at a location?

The modular physical architecture does not automatically solve these questions, but it creates a place in the architecture where they can be made explicit.

## Case exchange as physical configuration

The user should be able to change the phone's capabilities physically:

```
leave home
   ↓
remove home case
   ↓
install work / travel / field case
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

## Multiple cases and case inventory

A person could maintain a collection of cases rather than one universal case.

The collection might include:

- home;
- work/inspection;
- field;
- travel;
- laboratory;
- workshop;
- vehicle;
- accessibility;
- emergency;
- communications;
- environmental monitoring;
- geology;
- archaeology;
- oceanography.

The cases could be standardized enough that the same phone skeleton fits all of them.

A case could also be shared by multiple compatible phones if the architecture supports user/device authentication separately from physical connection.

That raises an important question: should the case belong to the person, the location, the organization, or the phone?

## Case as a physical tool ecosystem

The broader idea is not limited to the phone and its cases.

The cases themselves could be part of a repairable tool ecosystem.

A person might have:

```
PHONE SKELETON
      │
      ├── CASES
      │     ├── home
      │     ├── work
      │     ├── field
      │     ├── laboratory
      │     └── accessibility
      │
      └── TOOL KIT
            ├── diagnostic reader
            ├── module test fixtures
            ├── calibration tools
            ├── repair tools
            └── spare modules
```

The user could carry the phone while leaving specialized cases at appropriate places, and carry a small set of diagnostic and repair tools as part of the same ecosystem.

This preserves the central goal of human assembly and repair: the person remains able to understand the physical pieces, remove them, test them, replace them, and put the system back together.

## Serviceability

A modular phone should make the service path explicit:

```
symptom
  ↓
identify suspected module or case
  ↓
remove module/case
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

The architecture could support independent repair shops, schools, libraries, community workshops, field technicians, scientific users, and individual experimenters.

## Physical transparency versus software transparency

The concept intentionally has two kinds of inspectability.

Physical inspectability means the user can see and remove the modules and the case.

Software/system inspectability means the user can understand what the modules report, how they communicate, what sensors exist, and what diagnostic tools can observe.

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
28. What would a useful **general-purpose environmental sensing skin** contain?
29. What minimum sensor set would make a home/environment case genuinely useful without making it unnecessarily complicated?
30. How could a case support a **miniaturized radiation detector** while preserving calibration, shielding, safety, and independently verifiable measurements?
31. What sensor combinations are useful for geology?
32. What sensor combinations are useful for archaeology?
33. What sensor combinations are useful for oceanography and coastal field work?
34. What sensor combinations are useful for environmental-health inspection?
35. What sensor combinations are useful for workplace inspection?
36. Could a single case contain interchangeable sensor bays so that the user can configure the array for a particular assignment?
37. Should sensor modules themselves be removable from the case?
38. Can a home case operate as a persistent environmental-sensing station while the phone is away?
39. How should a phone authenticate and trust a case that belongs to a location rather than to the phone owner?
40. Can one standardized case interface support passive sensors, powered sensors, intelligent sensor platforms, and specialized computers?
41. What physical dimensions and connector arrangements would make cases interchangeable across generations of phone skeletons?
42. How should power be shared between a phone and a case?
43. Should a case be able to operate independently when the phone is absent?
44. How should sensor data be stored when the phone is away and synchronized when it returns?
45. How should physical switches on a case control microphones, cameras, radios, or other sensors?
46. Can the diagnostic reader test a complete case as well as individual modules?
47. How can calibration status and sensor provenance be represented and independently checked?
48. How can location-specific cases preserve privacy when they contain environmental or workplace sensors?
49. Could a case be shared among multiple compatible phones without confusing identity, authorization, or ownership?
50. What case types would be useful enough to justify maintaining a physical inventory?
51. Could libraries, workplaces, community laboratories, or households maintain shared case inventories?
52. What happens when a case is deliberately left at home, but the phone's owner needs its sensor data remotely?
53. Which functions should remain available through the phone when the case is absent?
54. Could the same phone skeleton support radically different cases without becoming too complex to configure safely?
55. What would a practical repair and calibration kit for these cases contain?
56. Could the same diagnostic reader identify not only the case but every sensor installed in it?
57. How should the system handle a case containing a mixture of consumer sensors and professionally calibrated instruments?
58. What measurements should be treated as exploratory observations versus measurements suitable for scientific, occupational, environmental, or regulatory use?
59. Could case designs be published so that people can build their own sensor skins?
60. What would be required for a human to physically assemble, disassemble, test, repair, recalibrate, and understand the complete phone-plus-case system without manufacturer-only tools?

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

## Relation to Garage-Scale Advanced Technology

The modular skeleton phone is a concrete example of the larger garage-scale question.

The objective is not simply to create a phone with many interchangeable parts.

It is to investigate whether a sophisticated device can remain:

- physically understandable;
- manually configurable;
- independently testable;
- repairable;
- locally maintainable;
- adaptable to different environments;
- open to third-party modules;
- capable of using specialized sensor skins;
- compatible with independent diagnostic tools.

The phone therefore serves as an architectural test case for technological agency.

## Status

This is a physical architecture concept, not a claim that all of these modules, sensors, cases, or instruments can currently be standardized at one practical size.

The central research problem is to investigate whether modern phone functionality can be reorganized into two cooperating modular systems—a portable computing skeleton and a removable technological skin—while retaining modern performance, safety, security, communications, measurement quality, and human repairability.

The sensor arrays described here are a research inventory, not a validated specification. In particular, radiation sensing, chemical sensing, scientific field measurements, physiological sensing, and other specialized measurements would require separate research into sensor technology, calibration, safety, environmental limits, and appropriate use.
