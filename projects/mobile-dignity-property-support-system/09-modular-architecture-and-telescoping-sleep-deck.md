
# 09 — Modular Architecture and Telescoping Sleep Deck

## Status

**PROPOSED / CONCEPTUAL — based on the September 21, 2026 paper sketch and discussion.**

This document records the architecture shown in the user's hand-drawn sketch. Dimensions and mechanisms remain preliminary until physically prototyped.

## Core idea

The system is not necessarily one complete vehicle. It is a **modular attachment ecosystem** built around a simple dolly/cargo base.

The major modules are intended to be independently removable:

1. **Dolly / cargo base**
2. **Riding module**
3. **Optional electric module**
4. **Telescoping sleeping deck**
5. **Shelter/tent module**
6. **Cargo case / suitcase**

The user should be able to use only the modules that are useful to them.

Examples:

- dolly only;
- dolly + cargo case;
- dolly + sleeping deck;
- dolly + riding module;
- dolly + riding module + electric assist;
- riding module with a different compatible attachment;
- sleeping deck with or without the riding system.

The long-term goal is to make the interfaces useful enough that people can experiment with other compatible attachments rather than being locked into one permanent configuration.

## Paper-sketch interpretation

The September 21 sketch shows three related configurations:

### Riding configuration

The upper drawing shows:

- an upright cargo case/dolly at the rear;
- a folding or telescoping riding assembly;
- a seat;
- a pedal/propulsion area;
- a rear solid wheel;
- a folding/arched control handle;
- a pivot/folding joint connecting the riding assembly to the dolly.

The riding assembly is intended to retract so that the system can return to a compact walking-dolly configuration.

### Sleeping configuration

The lower-left drawing shows a long flat deck extending from the lower portion of the dolly.

The intended mechanism is:

- nested flat panels;
- panels telescope outward one section at a time;
- each section has an integrated solid support block underneath or near its outer/front portion;
- as the sections extend, the support blocks progressively contact the ground;
- the extended panels form one continuous sleeping surface;
- the deck does not depend on separate folding legs or additional wheels;
- the entire deck nests flat when retracted.

The support blocks should be treated as **integrated ground-support blocks**, not conventional deployable legs.

### Walking configuration

The lower-right drawing shows the compact walking mode:

- riding assembly folded/retracted;
- upright cargo case retained;
- user pushes the dolly normally.

## Telescoping sleep-deck principle

The proposed sequence is approximately:

**Closed**

[Dolly][Panel 1][Panel 2][Panel 3][Panel 4]

**Beginning extension**

[Dolly][Panel 1]----

                  [Panel 2]----

                             [Panel 3]----

**Fully extended**

[Dolly]----[P1]----[P2]----[P3]----[P4]

Each panel remains structurally associated with its own support block.

The blocks are not intended to be separate pieces that a user must deploy manually. They are part of the panel architecture.

The approximate spacing discussed so far is **6–8 inches**, but this is only a starting hypothesis. Actual spacing must be determined by panel material, thickness, span, load, ground conditions, and required stability.

## Width concept

The user proposed keeping the complete mobility system within roughly a wheelchair/accessibility-related width envelope.

A **32–36 inch overall width range** is a preliminary design target, not a regulatory claim.

The sleeping surface may be approximately this wide as well, subject to actual human sleeping dimensions and structural requirements.

The design should distinguish:

- overall vehicle width;
- clear passage width;
- sleeping-surface width;
- wheel/steering clearance;
- cargo-case width.

These dimensions should not be assumed to be identical.

## Independent-section principle

Each telescoping deck section should ideally be independently replaceable.

Potential configurations include:

- fewer sections for a shorter bed;
- additional sections for a longer bed;
- removal of a damaged section;
- replacement of one worn or damaged section without replacing the entire deck;
- removal of the entire sleeping module when it is not wanted.

This supports the project's broader principles of:

- repairability;
- modularity;
- low replacement cost;
- local maintenance;
- user choice;
- reduced material waste.

## Product architecture

The emerging architecture can be represented as:

DOLLY BASE

├── CARGO CASE

├── RIDING MODULE

│   └── OPTIONAL ELECTRIC MODULE

└── TELESCOPING SLEEPING MODULE

    └── SHELTER / TENT

The modules should not be assumed to require permanent integration.

## Possible manufacturing strategy

A potentially efficient approach is to avoid manufacturing the entire dolly.

The project could instead develop:

**A. Standardized dolly interface**

A simple attachment/interface geometry.

**B. Riding module**

Seat + rear wheel + propulsion + braking + folding/telescoping structure + steering/control linkage as required.

**C. Electric module**

Battery + motor + controller + drive components, designed as a removable upgrade.

**D. Telescoping deck**

Nested panels + integrated ground-support blocks + retention/locking system.

**E. Shelter**

A separate tent/bivy system sized to the deployed deck.

Commodity components such as a suitable dolly, suitcase, tent fabric, fasteners, and panels could potentially be sourced separately.

## Important unresolved engineering issue: steering

A truly universal "attach this riding module to any dolly" system cannot be assumed.

Most ordinary dollies do not have steerable front wheels.

Therefore the project must eventually determine whether the attachment standard will:

1. connect to an existing steerable wheel assembly;
2. provide a steering linkage to the dolly's front wheels;
3. replace/adapt the dolly wheel assembly;
4. use a defined class of compatible dolly bases rather than literally any dolly.

This is a major open engineering question.

## Important unresolved engineering issue: telescoping guidance

The sleep deck needs a simple way to:

- remain aligned laterally;
- prevent sections from separating unintentionally;
- support vertical load;
- resist twisting;
- stop at the intended extension position;
- retract without binding;
- remain reasonably compact when closed.

A conventional drawer-slide mechanism is **not** assumed to be necessary. The preferred direction remains simple, inexpensive, repairable mechanical guidance if testing shows it is adequate.

## Design philosophy

The concept intentionally favors:

- few parts;
- simple geometry;
- visible mechanical relationships;
- replaceable sections;
- low-cost materials;
- repair rather than replacement;
- modular ownership;
- user experimentation;
- no unnecessary electronics;
- no requirement to purchase every module.

## Evidence classification

### KNOWN

- The paper sketch documents the intended relationship between walking, riding, and sleeping configurations.
- The user wants the sleeping deck attached to the lower portion of the dolly.
- The user wants nested/telescoping sections with integrated support blocks.
- The user wants modules to be independently removable.

### PROPOSED

- 32–36 inch approximate overall width envelope.
- 6–8 inch approximate support-block spacing.
- Independent replaceable deck sections.
- Separate manufactured riding module rather than a complete vehicle.
- Separate optional electric module.
- Standardized attachment interfaces.

### CALCULATED

None yet. Structural dimensions, loads, material thicknesses, wheel geometry, and required clearances have not been calculated.

### TESTED

None yet. The mechanism has not been physically prototyped.

### SPECULATIVE

- A very low-cost telescoping deck may be achievable without conventional commercial slide hardware.
- A useful semi-universal riding-module interface may be possible.
- The modules may be useful with compatible third-party or user-built attachments.

### UNKNOWN

- Exact deck width and sleeping length.
- Panel material and thickness.
- Number of telescoping sections.
- Support-block dimensions.
- Ground-load distribution.
- Lateral stability.
- Retention/locking method.
- Steering interface.
- Braking interface.
- Maximum safe rider/cargo load.
- Manufacturing cost after engineering and safety testing.

## Next prototype question

Before adding complexity, build or mock up only the **telescoping sleeping deck mechanism**.

The first physical test does not need a vehicle.

A simple tabletop/ground prototype using inexpensive flat material can answer the most important questions:

1. Can the panels telescope smoothly?
2. Can the integrated blocks support the extended panels?
3. Can the sections remain aligned without expensive slides?
4. Can one section be removed and replaced?
5. Does the whole assembly retract into a compact stack?
6. Can an adult's distributed weight be supported without excessive flex?

The riding mechanism can then be developed independently.

---

**Archive note:** This file records the concept as understood from the September 21, 2026 hand-drawn sketch. It should not be treated as a final engineering specification.
