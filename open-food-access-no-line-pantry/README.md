# Open Community Resource Access & No-Line Navigator

## Status

**PROPOSED / FOUNDATION** — This folder began as a food-access project and is now being generalized into an open-source, community-maintained resource-guide navigator. The food-access use case remains the first concrete implementation case. It is not a deployed service.

## Origin

The project started from a practical food-access problem: a person can have some formal resources available and still run out of usable food before the end of the month. The original design therefore focused on reducing lines, bureaucracy, wasted trips, unsuitable food, unnecessary data collection, and other barriers to actually obtaining useful food.

The broader lesson is that the same access problem can occur with many kinds of community resources.

## General purpose

The proposed system can ingest authorized community resource guides and other structured or semi-structured public resource information, then help a person answer:

> **What useful resource is available to me, where is it, can I use it, and what can I do next?**

Food is one resource category, not the architectural limit.

Potential categories may include:

- food and meals;
- housing and shelter;
- transportation;
- showers, restrooms, and hygiene;
- health and behavioral-health services;
- employment and workforce services;
- legal and civic assistance;
- libraries and community spaces;
- emergency and disaster resources;
- veteran services;
- disability and accessibility resources;
- benefits and public assistance;
- seasonal/community resources;
- other locally defined services.

## Community-guide network

A Santa Cruz Free Guide can be one source. A different community could contribute a similarly structured guide under another name.

The long-term model is collaborative:

**Guide / document / authorized source → structured resource records → provenance → verification → time/status/eligibility/access evaluation → concise next action**

A national-scale system should not depend on one organization owning the truth. Local maintainers should be able to correct, verify, expire, replace, or withdraw records while preserving provenance.

Automated discovery may eventually help locate candidate guides on the public internet, but discovery is **not verification**. A crawler or importer must never silently turn a found webpage or PDF into a claim that a service is currently available.

## What makes this different from a directory

A directory mainly answers “what exists?”

This project is intended to answer the more practical sequence:

1. What is near the person's stated location or community?
2. Is the resource relevant to the person's request?
3. Is it open, closed, appointment-only, seasonal, restricted, or unknown **right now**?
4. What eligibility or documentation requirements are actually stated?
5. Can the person realistically use the access path?
6. What is the smallest useful next action?
7. If that path fails, what context-preserving alternatives exist?

The system should do information work before asking the person to do work the system can already do.

## Open-source and low-barrier principles

- No app download or account should be required for a seeker where technically feasible.
- SMS, phone, keypad, and web interfaces may share the same underlying resource model.
- Community/self-hosted deployment should remain possible.
- Privacy minimization is a design requirement.
- Local language, cultural terminology, landmarks, and community corrections should be supported.
- A landmark clue is not the same thing as GPS.
- Unknown information must remain unknown rather than being presented as current availability.
- Travel capability is part of practical access, not a standalone pass/fail gate.
- The system should provide recovery, backtracking, pause, cancellation, and alternatives without blaming the user.

## Current foundation

The immediate implementation foundation is:

1. define a general resource-record schema;
2. create a small real fixture from the historical People First Santa Cruz Free Guide, clearly dated and not presented as current without verification;
3. evaluate time, status, eligibility, and access;
4. support provenance and verification;
5. connect the resulting records to the existing practice interface.

The first implementation can remain small while the data model is designed to support other guide types.

## Evidence labels

- **KNOWN:** User-described experience, stated requirements, or documented source material.
- **PROPOSED:** Design ideas not yet implemented or validated.
- **CALCULATED:** Derived technical or operational estimates.
- **TESTED:** Verified through an actual prototype or trial.
- **SPECULATIVE:** Possibilities requiring research.
- **UNKNOWN:** Unresolved questions.

## Guardrails

- Do not delete, merge, rename, or overwrite existing APO material without explicit approval.
- Preserve provenance and uncertainty.
- Uploading or discovering a document does not make its contents verified.
- Do not claim current availability without appropriate verification.
- Do not expose private-property locations or encourage trespass.
- Do not collect sensitive personal information merely because a resource guide contains it.
- Do not treat automated web discovery as authoritative.
