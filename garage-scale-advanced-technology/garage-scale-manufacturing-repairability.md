# Garage-Scale Manufacturing and Repairability

**Date:** 2026-09-18  
**Status:** Research direction.

## Core question

Can advanced technology become sufficiently modular, documented, and tool-supported that small workshops, schools, libraries, community laboratories, and individuals can participate meaningfully in building, testing, repairing, and modifying sophisticated devices?

“Garage-scale” refers to the scale of participation, not a claim that semiconductor fabrication or every advanced manufacturing process can literally happen in a garage.

## Older modular computing as a reference

The user's 386-era experience is an important reference point.

Computers could be understood as physical systems assembled from boards, processors, memory, storage, expansion cards, buses, cables, and other components.

A person could remove pieces, replace them, test them, and reconfigure the system.

The project asks whether that physical intelligibility can be preserved while technology becomes vastly more integrated.

## Manufacturing layers

Research should distinguish:

1. industrial fabrication of advanced components;
2. assembly of standardized modules;
3. local testing and diagnostics;
4. repair and replacement;
5. small-scale fabrication of compatible parts;
6. software and firmware modification;
7. education and experimentation.

A system does not have to make every semiconductor locally to provide meaningful local technological agency.

## Tools

A future workshop might need:

- diagnostic readers;
- electrical test equipment;
- optical test equipment;
- programming/debugging tools;
- standardized module fixtures;
- repair equipment;
- calibration tools;
- documentation;
- open reference designs;
- safe battery and power equipment;
- software development tools.

The actual tool list should be determined through research and experiments rather than assumed.

## Repairability as architecture

Repairability is strongest when it is designed into the physical system.

Possible sequence:

```
symptom
  ↓
identify module
  ↓
remove module
  ↓
test independently
  ↓
repair / replace
  ↓
retest
  ↓
reinstall
```

The independent diagnostic reader is therefore as important as the removable module.

## Local fabrication

Research questions include:

- Which modules could realistically be assembled locally?
- Which require industrial semiconductor fabrication?
- Which could use commercially available chips on open circuit boards?
- Which mechanical components could be locally fabricated?
- Which cases, connectors, fixtures, or adapters could be made in small workshops?
- Could standardized interfaces allow independent manufacturers to compete?
- Could community laboratories maintain module inventories?

## Safety and limits

Openness does not eliminate safety requirements.

Batteries, high-energy systems, radio transmitters, medical sensors, optical systems, and other components may have specialized safety or regulatory constraints.

The research should distinguish legitimate safety controls from unnecessary barriers to repair and experimentation.

## Research questions

1. What does a realistic garage-scale advanced technology workshop require?
2. What equipment could be shared through libraries or community laboratories?
3. Which functions can be localized and which remain industrial?
4. What standardized fixtures would make testing easier?
5. Can diagnostic readers be open and independently manufactured?
6. How can calibration remain trustworthy?
7. How can small manufacturers make compatible modules?
8. What documentation is necessary for repair?
9. What parts of the supply chain are most difficult to decentralize?
10. How does extreme miniaturization affect local repair?
11. Which technologies are likely to become more accessible as tooling improves?
12. What manufacturing knowledge should remain publicly teachable?
