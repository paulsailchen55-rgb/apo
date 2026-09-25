# Pure Data Research Overview

**Status:** RESEARCH / REFERENCE
**Project relationship:** Pure Data Housing Transmission Interface
**Research date:** 2026-09-25

## What Pure Data is

Pure Data (Pd) is a free, open-source visual programming environment originally developed for real-time computer music and interactive media. The official project describes it as a free real-time computer music system for Linux, macOS, and Windows.

For this project, the important idea is not music. It is the **patch/dataflow model**: a visible network of objects, messages, data, and connections that can both explain a process and execute it.

A Pd patch can function as:
- a visual explanation;
- an executable process model;
- an interactive simulation;
- a reusable module;
- a data-routing diagram;
- an interface to external software or hardware.

The housing project is investigating whether that model can represent a complicated administrative and physical transmission system.

## Core Pd concepts

### Objects
Objects are functional units placed in a patch. They can perform arithmetic, comparisons, routing, timing, list processing, table operations, file operations, network communication, MIDI, user-interface functions, and many other tasks.

### Connections
Connections show how information or control moves between objects. This makes relationships inspectable: where information comes from, what changes it, where it branches, and where it stops.

### Messages
Pd has a discrete message/control system. Messages can contain numbers, symbols, lists, and commands. Housing events such as application submitted, review completed, permit issued, construction started, or occupancy reached can conceptually be represented as messages.

### Signals
Pd also has a continuous signal-processing system, primarily for audio. The housing project probably does not need signal-rate processing, but the distinction demonstrates that Pd can represent different temporal behaviors in one environment.

### Arrays and tables
Pd supports arrays/tables for numerical series. Potential housing uses include review-time histories, unit counts, development costs, occupancy histories, and retention histories.

### Data structures
Pd has an advanced data-structure system for representing graphical and structured data. Current Pd documentation notes continued improvements to data structures, including easier traversal and support for messages or sequences of messages. This makes structured project/event representations worth investigating.

## Patches, subpatches, and abstractions

A large patch does not have to be one giant diagram. Pd supports subpatches, abstractions, reusable components, and graph-on-parent interfaces.

This creates a natural path toward the project's distance-to-detail idea.

Outer level:

NEED → PLAN → LAND → MONEY → PERMISSION → BUILD → HOME → PERSON

Then a component can be opened and expanded:

MONEY → funding need → application → review → award → closing → disbursement

The same approach can continue downward.

The goal is not to hide complexity. It is to make complexity navigable.

## Pd ecosystem layers

"Pure Data" is not one indivisible program. The ecosystem includes:

1. Pd Vanilla, the core/reference distribution.
2. Built-in objects and examples.
3. Abstractions, which are reusable Pd patches.
4. Externals, compiled objects that extend Pd.
5. Libraries, collections of abstractions and/or externals.
6. GUI plugins, which extend the graphical environment.
7. Deken, the package-management system.
8. Alternative Pd environments such as PlugData and Purr Data.
9. Embedded Pd through libpd.
10. Plugin wrappers such as Camomile and PlugData's plugin builds.

These categories should remain distinct in the project.

## Deken

Deken is Pd's built-in package manager for external libraries and objects. Its documentation says it is mainly targeted at Pd Vanilla, although it can also be used with some other Pd flavours.

Deken packages can contain Pd patches, compiled externals, help patches, tutorials, and binaries for different operating systems, CPUs, and Pd float sizes.

For reproducible research, record:
- Pd version;
- operating system;
- CPU architecture;
- external libraries;
- exact library versions;
- patch version;
- data schema version.

## Externals and libraries

An external is compiled code that adds an object to Pd. Libraries group related functionality.

Important ecosystem categories for this project include:
- networking;
- OSC;
- serial communication;
- data/list/matrix processing;
- graphics;
- hardware interfaces;
- Max/MSP compatibility.

Pd-lib-builder is a commonly used build helper for Pd externals.

## GUI plugins

Pd's graphical interface itself has a plugin architecture. The current Pd source contains plugin loading and a Tcl/Tk-based GUI.

Therefore the project should use precise terminology:
- **external** = compiled Pd object;
- **abstraction** = reusable Pd patch;
- **library** = package/collection;
- **GUI plugin** = graphical-interface extension;
- **host/plugin wrapper** = software embedding or packaging Pd for another environment.

## Why Pd is interesting for the housing project

The strongest match is:

**visible topology + executable behavior + modularity + timing + external communication**

The Housing Transmission Audit already uses transitions:

NEED → GOAL → CAPACITY → PROJECT → FINANCING → APPROVAL → PERMIT → CONSTRUCTION → OCCUPANCY → AFFORDABILITY → RETENTION → STABILITY

Pd can represent stages as objects/subpatches and transitions as explicit connections.

A kink point can become a visible interface.

A friction variable can become an input.

A loss can become a measured output.

A missing connection can remain visibly unconnected rather than being silently invented.

## What Pd does not establish

This research does not establish that:
- Pd should replace databases;
- Pd should replace GIS;
- Pd should replace permitting software;
- Pd should become a government standard;
- visual programming automatically makes a system understandable;
- every housing process can be represented accurately by a patch.

The narrower claim is:

> Pd provides a technically interesting model for representing, inspecting, and experimenting with complex dataflow.

## Relationship to the standardized-data project

The proposed architecture is:

GOVERNMENT STANDARD DATA
↓
CONVERSION / VALIDATION LAYER
↓
PURE DATA OBJECTS / PATCH
↓
VISUAL EXPLANATION + EXPERIMENTATION

The government does not need to use Pd.

The research question is whether a well-defined public data structure can be converted into Pd without losing identity, provenance, timestamps, definitions, status, uncertainty, jurisdiction, or event history.

## Evidence status

### KNOWN
- Pd is an established free/open-source visual programming environment.
- Pd is cross-platform.
- Pd supports patches, objects, messages, signals, arrays, data structures, abstractions, and external extensions.
- Deken is a package manager for Pd external libraries/objects.
- The ecosystem includes networking, OSC, graphics, serial, matrix, and other extensions.
- libpd provides an embeddable Pd core.
- PlugData provides another modern Pd-based environment and plugin/standalone packaging.

### CALCULATED / INFERRED
- The patch/dataflow model is structurally compatible with a visual representation of a staged housing transmission chain.
- Nested patches could support the desired distance-to-detail navigation.

### PROPOSED
- Use Pd as a research and demonstration layer over standardized housing project data.
- Preserve authoritative evidence in ordinary data files and Markdown rather than in the patch alone.

### SPECULATIVE
- A future "fractal zoom" housing interface could use nested Pd abstractions as its visual implementation.
- A standardized project record could be automatically converted into a Pd patch or object graph.

## Primary references

- Pure Data: https://github.com/pure-data/pure-data
- Pd documentation: https://msp.ucsd.edu/Pd_documentation/
- Deken: https://deken.puredata.info/
- pd-lib-builder: https://github.com/pure-data/pd-lib-builder
- libpd: https://github.com/libpd/libpd
- PlugData: https://github.com/plugdata-team/plugdata
- ELSE: https://github.com/porres/pd-else
- Cyclone: https://github.com/porres/pd-cyclone
- Gem: https://github.com/umlaeute/Gem
