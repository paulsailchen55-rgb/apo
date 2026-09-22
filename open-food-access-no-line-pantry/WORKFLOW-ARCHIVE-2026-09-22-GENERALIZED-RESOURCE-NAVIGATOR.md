# Workflow Archive — 2026-09-22 — Generalizing the Resource Navigator

## Classification

**PROPOSED / FOUNDATION**

## What changed

The project began as an open-source food-access/no-line pantry navigator. During reconciliation, a broader reusable architecture became apparent: the underlying problem is not exclusively food. Community resource guides often contain many kinds of assistance, and the same information-access workflow can serve them.

The food use case remains the origin and first implementation target.

## Core insight

**Food was the entry point; resource access is the reusable system.**

The person should not have to know the correct agency name, current schedule, eligibility language, or category before the system can begin helping.

## Generalized flow

**Community guide → structured resource record → provenance → verification → time/status → eligibility → location/access → next action**

This retains the work already done on:

- low-barrier text/keypad interaction;
- landmark-based wayfinding;
- time-aware routing;
- eligibility and documentation;
- travel/accessibility;
- temporary and seasonal information;
- privacy minimization;
- no-dead-end recovery;
- calendar output.

## Collaboration model

The proposed system can accept community guides from many places and organizations.

A future automated discovery process may find candidate guides across the public web, but it must not treat discovery as verification.

**Found is not verified. Uploaded is not verified. Extracted is not verified.**

Verification state and provenance must travel with each record.

## Immediate implementation consequence

Do not build a giant national crawler first.

Build the reusable resource-record foundation with one real local guide. Then demonstrate that the same record model can represent both a food resource and a non-food resource.

## Evidence status

- Generalization from the project's existing architecture: **PROPOSED**
- Food-access origin: **KNOWN**
- National automated discovery: **SPECULATIVE**
- Common resource schema: **PROPOSED**
- Real-guide fixture: **NEXT**
- Current resource availability: **UNKNOWN until independently verified**

## Next waypoint

Create:

- data/resource-record.schema.json
- data/fixtures/people-first-2025-01-19.json

Then implement time/status evaluation and test the model with at least one non-food resource record.

## Guiding principle

**Preserve the local guide; generalize the interface.**
