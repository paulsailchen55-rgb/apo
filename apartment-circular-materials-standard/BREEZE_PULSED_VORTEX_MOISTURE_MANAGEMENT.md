# Breeze — Pulsed Vortex Moisture Management

## Status

This is a new Breeze technical research track.

Evidence labels used here:

- **KNOWN** — supported by established physical principles or documented research.
- **CALCULATED** — derived quantitatively from stated assumptions.
- **TESTED** — experimentally demonstrated for this Breeze concept.
- **PROPOSED** — engineering hypothesis to investigate.
- **SPECULATIVE** — plausible but currently weakly supported.
- **UNKNOWN** — unresolved.

Current status: **PROPOSED / UNKNOWN**. No claim is made that this architecture can yet remove moisture at the required residential comminution rate.

## Core Observation

The moisture problem may be a rate problem rather than simply a drying problem.

During material reduction, moisture can appear simultaneously as:

1. free liquid;
2. liquid droplets;
3. wet/cohesive particles;
4. water vapor.

A conventional condenser primarily addresses vapor after it has entered an air stream. Breeze may need to manage moisture at the same time scale as the pressure pulses and material-fracture events.

**Design question:**

> Can moisture be separated, cooled, condensed, coalesced, and removed within the residence time of a Breeze pressure pulse or short pulse train?

## Concept

Investigate a **Pulsed Vortex Moisture Separator** using some combination of:

- compressed-air pulses already available to Breeze;
- Tesla-valve-like asymmetric flow geometry;
- contraction/expansion or nozzle geometry;
- vortex generation;
- rapid local pressure/velocity changes;
- temperature separation or expansion cooling;
- condensation/nucleation;
- droplet coalescence;
- centrifugal and/or gravity separation;
- a sealed liquid collection region.

The objective is not to make one large conventional condenser work harder.

The objective is to **manage moisture during the transient flow event itself**.

## Why Tesla-Valve Geometry Is Relevant

A Tesla valve is a passive fluidic geometry that creates different flow resistance in different directions through flow separation, recirculation, jet interaction, and vortex formation. Research has also shown that pulsating flow can materially affect Tesla-valve behavior and strengthen transient vortex structures.

A 2026 Nature Communications study is especially relevant to this research direction because it used reverse-Tesla-valve geometry to create vortex airflow and substantially alter heat and mass transfer at a gas-liquid interface.

These results do **not** demonstrate Breeze condensation. They support investigating Tesla-inspired geometry as a way to manipulate transient airflow and heat/mass transfer.

## Proposed Flow Sequence

Conceptual sequence:

**compressed-air pulse**
→ **Tesla-like flow geometry**
→ **acceleration / expansion**
→ **vortex formation**
→ **local cooling / temperature separation**
→ **vapor reaches saturation**
→ **condensation / droplet formation**
→ **droplet coalescence**
→ **gravity and/or centrifugal separation**
→ **sealed water collection**
→ **remaining air proceeds to particulate and boundary-air management**

The exact order may need to change during testing.

## Do Not Treat All Moisture the Same

The system should investigate separate pathways:

### Free liquid

Preferred response:

**gravity / drainage / mechanical separation**

Do not spend energy vaporizing water that can simply be collected.

### Droplets

Preferred response:

**coalescence + inertial/centrifugal separation**

The goal is to make small droplets become larger droplets that can be removed rapidly.

### Wet particles

Potential response:

**classification, surface shedding, coalescence, or dedicated wet-fraction pathway**

Wet particles may not behave like dry particles and may interfere with acoustic transport.

### Vapor

Potential response:

**rapid cooling / expansion / vortex-assisted condensation followed by liquid separation**

A conventional condenser remains a possible downstream polishing stage rather than necessarily the primary moisture-removal mechanism.

## Pulsed Operation

Breeze already has a conceptual compressed-air pulse architecture for material reduction.

The moisture-management subsystem could therefore investigate synchronized pulse phases:

**reduction pulse**
→ material fracture and moisture release

**separation phase**
→ flow geometry redirects liquid/droplets and creates vortices

**condensation phase**
→ local cooling and pressure/velocity changes encourage vapor condensation

**drain phase**
→ collected liquid moves to a sealed reservoir

**classification phase**
→ dry particles continue toward size classification/collection

This could potentially repeat rapidly without requiring a large continuously operating refrigeration loop.

## Multiple Tesla-Pattern Regions

A further **PROPOSED** concept is to use several Tesla-like structures around or along a flow passage rather than a single valve.

Possible objectives:

- alternate vortex direction;
- increase mixing without a mechanical rotor;
- repeatedly interrupt boundary layers;
- create controlled recirculation zones;
- encourage droplets to collide and coalesce;
- steer liquid toward known collection surfaces;
- synchronize fluidic behavior with pressure pulses.

A three-dimensional or circumferential arrangement is an open research question.

## Vortex-Tube Connection

A Ranque–Hilsch vortex tube is another technology worth investigating because compressed air can produce separated hot and cold streams without a conventional refrigeration compressor.

Potential Breeze role:

**compressed-air pulse**
→ **vortex temperature separation**
→ **cold stream**
→ **targeted condensation zone**

This remains **PROPOSED**, and the energy/flow penalty must be quantified. The vortex tube should not be assumed to provide free cooling.

## Critical Thermal Constraint

Condensation does not eliminate energy.

When water vapor condenses, latent heat must be transported somewhere. Therefore:

**cooling the air**
≠
**removing the heat**

The design must identify the heat sink and quantify:

- inlet air temperature;
- inlet humidity;
- pressure;
- pulse duration;
- mass flow;
- cold-stream temperature;
- condensation rate;
- latent heat released;
- heat rejected;
- pressure drop;
- electrical/compressed-air energy cost.

## Key Hypothesis

The most important hypothesis is:

> **Breeze may be able to reduce the required conventional condenser capacity by removing liquid and droplets mechanically first, using pulsed vortex/flow geometry to promote rapid condensation of only the remaining vapor fraction.**

This is deliberately narrower than claiming that a Tesla valve itself is a condenser.

## Experimental Questions

1. How much moisture is released per kilogram of each feedstock class?
2. What fraction appears as free liquid, droplets, wet particles, and vapor?
3. What is the moisture-release rate during an individual reduction pulse?
4. What pressure and pulse duration are required to produce useful vortex structures?
5. Does Tesla-inspired geometry increase droplet coalescence?
6. Can a vortex/expansion stage produce sufficient local cooling?
7. What fraction of vapor actually condenses during one pulse?
8. How quickly can condensate be removed from the flow?
9. Does condensate re-enter the particulate stream?
10. Does moisture cause clogging or fouling?
11. What happens when the input is deliberately wet?
12. What happens during condensation at cold surfaces?
13. Can the system recover between pulses?
14. What is the pressure-drop penalty?
15. Does the moisture-management subsystem increase acoustic output?
16. Can the entire pathway remain sealed from the occupied apartment?

## Initial Test Architecture

Do not begin with the full Breeze machine.

Build a small transparent or otherwise instrumented fluidic test section.

Measure:

- pressure before and after each geometry;
- pulse pressure waveform;
- flow rate;
- air temperature;
- relative humidity;
- dew point;
- condensate mass;
- droplet-size distribution if practical;
- collection efficiency;
- pressure drop;
- energy/compressed-air consumption.

First compare:

**plain tube**
vs.
**Tesla-inspired channel**
vs.
**Tesla-inspired channel + contraction/expansion**
vs.
**Tesla-inspired channel + vortex stage**
vs.
**Tesla-inspired channel + vortex stage + coalescing/collection geometry**

That isolates what each element contributes.

## Success Criterion

The primary metric should not be “did condensation occur?”

It should be:

> **grams of water removed per second per unit of pressure/energy input while maintaining the required particulate-flow behavior.**

Secondary metrics:

- g water / pulse;
- g water / kg feedstock;
- % moisture captured;
- pressure drop;
- compressed-air consumption;
- thermal rejection rate;
- particle-loss rate;
- fouling rate;
- acoustic impact.

## Evidence Status

**KNOWN**

- Tesla-valve geometries can generate asymmetric flow resistance through recirculation, separation, and vortex effects.
- Pulsating flow can change Tesla-valve behavior and strengthen transient flow structures.
- Tesla-inspired geometries have been demonstrated in two-phase and thermal-management research.
- Vortex tubes can produce temperature separation from compressed air.

**PROPOSED**

- Synchronizing Tesla-inspired flow geometry with Breeze pressure pulses.
- Using transient vortex structures to enhance moisture transfer.
- Combining condensation with rapid droplet coalescence and mechanical separation.
- Using multiple Tesla-pattern regions around a flow path.
- Using a vortex-tube-like stage as a targeted cooling mechanism.
- Treating conventional condensation as a residual-vapor polishing stage.

**UNKNOWN**

- Whether sufficient water can be removed during a Breeze pulse.
- Whether the pressure/energy cost is compatible with residential operation.
- Whether condensation can occur without unacceptable particulate fouling.
- Whether the proposed geometries can operate reliably with mixed dust, droplets, fibers, and debris.
- Whether the resulting thermal load can be rejected safely.
- Whether the concept can meet the desired overnight residential cycle time.

**TESTED**

- None for Breeze at this stage.

## Research Note

A 2026 Nature Communications paper reported that reverse-Tesla-valve structures can generate vortex airflow and strongly modify gas-liquid heat/mass transfer. Earlier work has also demonstrated Tesla-valve behavior in two-phase thermal systems and shown that pulsatile flow can enhance Tesla-valve diodicity. These are relevant precedents, but they are not direct validation of the Breeze application.

## Next Step

Before selecting a final condenser, test the more fundamental proposition:

**Can Breeze's own pulsed compressed-air energy be used to create a fast fluidic moisture-separation event?**

If yes, the downstream condenser may become substantially smaller because it is no longer being asked to solve the entire moisture problem.
