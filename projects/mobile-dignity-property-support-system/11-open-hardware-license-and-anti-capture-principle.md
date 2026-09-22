# 11 — Open Hardware License and Anti-Capture Design Principle

## Proposed licensing direction

The project should be developed as **open-source hardware**, rather than as a closed proprietary product.

The recommended starting license for the project's original hardware design files is:

**CERN Open Hardware Licence Version 2 — Strongly Reciprocal (CERN-OHL-S v2).**

CERN describes OHL v2 as a legal framework for allowing hardware designs to be used, studied, modified, shared, and distributed. The S variant is the strongly reciprocal option. The definitive license text is maintained by CERN. See:

https://cern-ohl.web.cern.ch/

This recommendation is about the **project's original design files and documentation**. It does not change the ownership or licensing terms of third-party components that may be incorporated into a build.

## Why this fits the project

The intended design philosophy is not:

> manufacture every component ourselves and control the entire product.

It is closer to:

> identify inexpensive, commonly available parts; design simple interfaces between them; document the complete assembly; allow people to build, repair, modify, replace, or manufacture compatible versions.

Open hardware is specifically compatible with this approach. The Open Source Hardware Association describes open hardware as designs made publicly available so people can study, modify, distribute, make, and sell the design or hardware based on it, with a preference for readily available components and standard processes.

## Anti-capture principle

The project should explicitly state:

> **The design is intended to remain a public, modular, repairable hardware design rather than becoming dependent on a single manufacturer or proprietary supply chain.**

The project should favor:

- standard fasteners;
- common wheels and bearings where practical;
- commercially available motors and batteries where appropriate;
- replaceable panels;
- commodity cargo cases;
- ordinary tent/shelter components;
- simple fabrication methods;
- documented dimensions and interfaces;
- multiple possible suppliers;
- local repair;
- user modification;
- independently replaceable modules.

## What the license does and does not do

A strong reciprocal open-hardware license can require covered derivative hardware designs to remain available under compatible open terms.

It **does not mean that corporations are forbidden from using the design**.

A company could potentially manufacture and sell a compliant product. The important distinction is that the company would not automatically acquire exclusive ownership of the open design merely by manufacturing it.

Therefore the goal is not "no corporate use."

The goal is:

> **No exclusive corporate control over the project's openly licensed core design.**

A manufacturer can participate, improve the design, produce it at scale, and sell it, while the underlying covered design remains available under the project's open-hardware terms.

## Existing parts principle

The project should deliberately separate:

### Original project design

Examples:

- attachment geometry;
- modular interfaces;
- riding-module structure;
- telescoping deck architecture;
- integrated ground-support-block arrangement;
- documented assembly methods;
- project-specific mechanical drawings.

These are the materials for which an open-hardware license should be considered.

### Third-party components

Examples:

- suitcase/cargo case;
- wheels;
- bearings;
- bicycle pedals;
- brake components;
- motors;
- batteries;
- controllers;
- tent fabric or commercially available tents;
- fasteners;
- tubing;
- panels.

These remain subject to their own manufacturers' terms, patents, trademarks, certifications, and safety requirements.

The project should not imply that an open-hardware license grants rights to someone else's proprietary component.

## Patent question

A patent is a different tool from a license.

A U.S. utility patent can provide an inventor with the right to exclude others from making, using, offering for sale, selling, or importing the claimed invention for a limited period. The USPTO also states that an invention generally needs to be new and non-obvious to qualify, and publicly available material can affect patentability.

Therefore, choosing an open-hardware license is a meaningful strategic decision.

If the project is intentionally published as an open design, the project should **not simultaneously assume that a later patent can automatically be obtained on everything publicly disclosed**.

Before deliberately pursuing patent protection, perform a prior-art search and obtain appropriate patent advice.

## Copyright question

Copyright is useful for the project's original expressive materials such as:

- drawings;
- photographs;
- written documentation;
- diagrams;
- software, if later included.

Copyright does not function as the primary protection for the underlying mechanical invention. The USPTO distinguishes copyright from patents: copyright protects creative works, while patents address inventions and certain designs.

Therefore:

**Copyright:** useful for the drawings and documentation.

**Patent:** potentially relevant to a genuinely new mechanical invention, if patent protection is desired and the requirements are met.

**Open-hardware license:** the preferred tool for making the project's covered hardware design available to others while establishing the conditions for reuse and modification.

## Project policy

Unless this policy is deliberately changed later, the working direction is:

1. Keep the core design public.
2. Prefer open documentation and reproducible fabrication information.
3. Prefer ordinary, replaceable components.
4. Avoid unnecessary proprietary dependencies.
5. Do not claim ownership of third-party parts.
6. Allow commercial manufacture under the applicable open-hardware terms.
7. Do not treat corporate participation as the same thing as corporate ownership.
8. Preserve the ability of individuals, nonprofits, small fabricators, and communities to build and repair compatible systems.

## Important status

This is a **project licensing recommendation, not legal advice**.

The project has not yet established a final legal license notice for every future design artifact. Before commercial release, patent filing, certification, or formal licensing, the exact license scope and any patent strategy should be reviewed.

## Primary references

- CERN Open Hardware Licence: https://cern-ohl.web.cern.ch/
- Open Source Hardware Association definition: https://oshwa.org/definition/
- USPTO — Trademark, Patent, or Copyright: https://www.uspto.gov/trademarks/basics/trademark-patent-copyright
- USPTO — Patent Essentials: https://www.uspto.gov/patents/basics/essentials

---

**Archive note:** The central project principle recorded here is not "keep corporations out." It is "keep the core design from becoming exclusively controlled by any single organization." The system should remain buildable from existing components and documented interfaces wherever practical.
