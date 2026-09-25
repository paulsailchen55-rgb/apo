# Pure Data Externals and Libraries

**Status:** RESEARCH / ECOSYSTEM MAP

## Why the ecosystem matters

Pure Data is extended through abstractions, compiled externals, libraries, GUI plugins, and related environments.

Important distinctions:
- **abstraction** = reusable Pd patch;
- **external** = compiled Pd object;
- **library** = collection of objects/abstractions;
- **GUI plugin** = graphical-environment extension;
- **variant** = another Pd-based environment.

## Deken

Deken is Pd's built-in package manager for external libraries and objects.

Its documentation describes packages that may contain:
- Pd patches;
- compiled externals;
- help patches;
- tutorials;
- platform-specific binaries;
- source packages.

Packages identify supported operating systems, CPU architectures, and Pd float sizes.

For reproducibility, record exact versions and architectures.

## ELSE

ELSE (EL Locus Solus' Externals) is a large library of Pd objects and abstractions maintained by Alexandre Porres and contributors.

Its documentation says it grew beyond its original teaching role into a large collection of objects and abstractions. Current releases remain in a release-candidate phase, with compatibility changes possible before final 1.0 stabilization.

Potential relevance:
- data manipulation;
- control structures;
- timing;
- interfaces;
- reusable abstractions.

The housing project should not make ELSE a hidden dependency unless a working prototype actually requires it.

## Cyclone

Cyclone is a library of Pd objects cloned from Max/MSP, providing compatibility for people working across Max and Pd.

The current repository reports Cyclone 0.9-4, released February 2026, requiring Pd Vanilla 0.56-2 or newer.

Its relevance here is architectural: a visual programming environment can gain a large compatibility library without changing its basic patch model.

## IEM ecosystem

The IEM Pd distribution includes:
- iemlib;
- iemmatrix;
- iem_ambi;
- iem_tab;
- comport;
- iemnet;
- net;
- osc;
- zexy;
- arduino;
- windowing;
- list-abs;
- bsaylor.

Several are interesting for the housing project.

### iemmatrix
Potential matrix/data transformations.

### iemnet / net
Network communication.

### osc
Open Sound Control messaging.

### comport
Serial communication.

### arduino
Physical-device interfaces.

### zexy
General-purpose utilities and data processing.

## Gem

Gem (Graphics Environment for Multimedia) adds graphics/multimedia capabilities to Pd. Its current repository lists Pd, OpenGL, and GLU as hard requirements.

Potential future use:
- animated system diagrams;
- spatial visualizations;
- interactive 2D/3D views.

It should not be required for the first housing prototype.

## Networking

Network-oriented libraries are particularly relevant because the proposed housing architecture separates authoritative data from the visual model.

Possible chain:

DATA SOURCE → NETWORK / DATA SERVICE → Pd

or:

Pd → NETWORK → another application

Relevant technologies include UDP, TCP, OSC, FUDI/Pd messaging, and serial communication.

## OSC

OSC is a message protocol widely used in interactive systems.

Pd can use OSC libraries to route structured messages. For example:

/housing/project/123/status occupied

or:

/housing/project/123/units 48

These are examples only.

An OSC transport does not define what "occupied" means, where the value came from, or how it is corrected. The data model must be defined separately.

## Hardware and serial extensions

Pd can connect to microcontrollers and serial devices.

A physical demonstration could map a control to a housing variable such as review delay and show the downstream model change.

That would be an educational simulation, not evidence about real government performance.

## Building new externals

pd-lib-builder is a helper build system used by many Pd libraries, including Cyclone, ELSE, and IEM projects.

A custom compiled external is therefore possible.

But the project should prefer:
1. Pd Vanilla;
2. ordinary abstractions;
3. well-maintained existing libraries;
4. custom externals only when a specific requirement is demonstrated.

## Dependency risks

### Version drift
A patch may behave differently after library updates.

### Architecture differences
A package may support one OS/CPU but not another.

### Dependency chains
One library may depend on additional software.

### Namespace collisions
Different libraries can expose similar object names.

### Hidden dependencies
A patch may work only because of an unrecorded local search path.

### Licensing
Libraries have different licenses.

### Abandonment
Historical Pd libraries may no longer be maintained.

### Documentation quality
Help files vary in completeness.

## Recommended dependency policy

### Level A
Pd Vanilla only.

### Level B
Pd Vanilla plus one necessary, well-maintained library.

### Level C
Several libraries with a documented dependency manifest.

### Level D
Custom/experimental externals.

The first housing prototype should remain at Level A or B if possible.

## Portability principle

The housing data must remain meaningful even if Pd or a particular library disappears.

Therefore:

**DATA ≠ PATCH**

The patch is a consumer of the data.

The authoritative record remains the standardized machine-readable project record.

## References

- Deken: https://deken.puredata.info/
- ELSE: https://github.com/porres/pd-else
- Cyclone: https://github.com/porres/pd-cyclone
- IEM Pd distribution: https://github.com/iem-projects/pd-iem
- Gem: https://github.com/umlaeute/Gem
- pd-lib-builder: https://github.com/pure-data/pd-lib-builder
- Pure Data: https://github.com/pure-data/pure-data
