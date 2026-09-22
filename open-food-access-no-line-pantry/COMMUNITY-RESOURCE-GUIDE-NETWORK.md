# Community Resource Guide Network

## Purpose

This document records the generalization of the original food-access project into a reusable open-source **community resource-guide navigator**.

The original problem remains important: food access was the concrete case that exposed the deeper problem of information access. A person may know that resources exist and still be unable to use them because the information is outdated, scattered, conditional, difficult to interpret, geographically disconnected, or presented without a practical next step.

## General model

The reusable unit is a **resource record**, not a food pantry record.

A resource record can represent a pantry, meal, shelter, shower, clinic, library program, benefits office, transportation service, legal clinic, veteran service, community garden, seasonal distribution, or another authorized service.

Core pipeline:

**Source → Ingestion → Resource Record → Provenance → Verification → Evaluation → Access Path → Action**

## Guide interoperability

A local guide does not need to use the same name as another guide.

Examples of source types:

- Santa Cruz Free Guide
- Santa Cruz Resource Guide
- city/county service guide
- veteran resource guide
- nonprofit directory
- community flyer
- public agency publication
- authorized service-provider page

The system should map these different source formats into a common record model while retaining the original source and local terminology.

## Automated discovery

A future discovery service could periodically search for candidate guides, feeds, PDFs, webpages, and update notices.

Discovery should produce **candidate sources**, not verified services.

A safe lifecycle is:

**DISCOVERED → EXTRACTED → NEEDS REVIEW → VERIFIED → ACTIVE → EXPIRED / WITHDRAWN**

A source may also be rejected or quarantined.

Automated extraction should preserve:

- source URL or document identity;
- publisher;
- publication/version date when available;
- retrieval date;
- page/section;
- language;
- extracted text;
- extraction confidence;
- verification state.

## Local collaboration

Communities should be able to:

- upload a guide;
- correct a record;
- verify a service;
- report a change;
- set an expiration;
- withdraw an outdated record;
- replace a guide with a newer version;
- preserve the relationship between old and new versions.

Local knowledge should be treated as valuable evidence, while still distinguishing a community report from formal provider verification when that distinction matters.

## Time and practical access

A resource is not simply “available” because it appears in a guide.

Evaluation may include:

- current day and local time;
- published hours;
- holidays and temporary closures;
- appointment versus walk-in access;
- eligibility;
- documentation requirements;
- service capacity or quantity when known;
- location;
- accessibility;
- travel/carrying constraints;
- language;
- seasonal or temporary status.

Possible output states include:

- OPEN / ACTIONABLE
- CLOSED / NEXT KNOWN OPENING
- 24/7
- ELIGIBILITY-RESTRICTED
- TEMPORARILY UNAVAILABLE
- UNKNOWN / NEEDS VERIFICATION

## National reuse without national centralization

The architecture can be national in scope without requiring a single national editor.

A local community can maintain its own source collection and resource records. A larger index could exchange records using documented schemas and provenance rules.

The reusable contract is the important part:

> **Any community should be able to publish resource information in a form another compatible navigator can understand.**

## Boundary

This document does not claim that automated nationwide discovery, verification, eligibility interpretation, or real-time availability is solved.

Those are implementation and governance questions.

The immediate goal is smaller: make one real community guide understandable as structured resource data, then prove that the same model can represent a non-food resource without breaking the access flow.
