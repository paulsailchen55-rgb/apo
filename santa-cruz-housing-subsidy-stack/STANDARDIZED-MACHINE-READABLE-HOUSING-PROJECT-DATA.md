# Standardized Machine-Readable Housing Project Data

## Status

**PROPOSED / RESEARCH DIRECTION**

This document records a data-interface requirement emerging from the Housing Transmission Audit and the proposed Pure Data interface.

It is not a request to create another government database before existing systems are understood.

## The Core Requirement

What the research appears to need is a:

> **Standardized, machine-readable housing project data structure with persistent identifiers, compatible definitions, and a conversion path into other analytical and visualization systems.**

The goal is interoperability.

A housing project should be able to move through different government systems without becoming a different, unrecognizable object every time it changes hands.

Conceptually:

**GOVERNMENT STANDARD DATA**
→ **CONVERSION LAYER**
→ **PURE DATA OBJECT / PATCH PACKAGE**
→ **VISUALIZATION / SIMULATION**

The conversion layer should make the process repeatable rather than requiring a person to manually rebuild the model for every jurisdiction or project.

## Why a Persistent Identifier Matters

A project may appear in many systems:

- Housing Element / RHNA reporting
- sites inventory
- planning
- zoning
- entitlement
- financing
- permitting
- construction
- occupancy
- affordable-housing monitoring
- preservation
- homelessness / supportive-housing systems where applicable

The same project needs a durable identifier that allows those records to be connected.

The California Department of Housing and Community Development's data strategy explicitly identified tracking the housing development pipeline from initial application through occupancy as a goal and recommended unique identifiers that allow projects to be mapped and tracked through the full development process. citeturn0search12

This is therefore not merely a Pure Data requirement. It corresponds to an existing public-sector data problem already identified by HCD.

## Minimum Conceptual Data Structure

A first common structure could contain fields such as:

```
PROJECT_ID
SITE_ID / APN
JURISDICTION
PROJECT_NAME
PROJECT_TYPE
UNIT_COUNT
AFFORDABILITY
APPLICATION_DATE
ENTITLEMENT_DATE
FINANCING_STATUS
PERMIT_DATE
CONSTRUCTION_START
COMPLETION_DATE
OCCUPANCY_DATE
CURRENT_STATUS
```

This is only a conceptual starting point.

The actual field list, definitions, allowable values, provenance rules, update rules, and privacy boundaries would need to be established through research.

## Event-Based Extension

The project identifier could then connect records across stages:

```
PROJECT_ID → APPLICATION
PROJECT_ID → REVIEW
PROJECT_ID → FINANCING
PROJECT_ID → APPROVAL
PROJECT_ID → PERMIT
PROJECT_ID → CONSTRUCTION
PROJECT_ID → COMPLETION
PROJECT_ID → OCCUPANCY
PROJECT_ID → AFFORDABILITY
PROJECT_ID → RETENTION
```

This would allow the transmission audit to ask what happened between stages without requiring every stage to be managed by the same agency or database.

## Instant Conversion as a Design Goal

The desired workflow is:

**STANDARD GOVERNMENT DATA**
→ import
→ validate
→ map fields
→ preserve provenance
→ convert
→ **PURE DATA OBJECTS**

The same standardized source should ideally be usable by other systems as well.

For example:

**Government data**
→ Pure Data

or

**Government data**
→ GIS

or

**Government data**
→ spreadsheet / database

or

**Government data**
→ dashboard

or

**Government data**
→ another jurisdiction's compatible tool.

The objective is therefore not to make Pure Data the required government technology.

The objective is to make the **data portable enough that Pure Data is one possible consumer of it**.

## Multiple-Jurisdiction Design

If the underlying structure is genuinely standardized, the same conversion layer could eventually accept records from:

- Santa Cruz County
- City of Santa Cruz
- another California city
- another California county
- potentially other jurisdictions using compatible standards.

The visualization or simulation layer should not have to be rewritten merely because the source jurisdiction changes.

The jurisdiction would become data.

## Important Distinction: Standardized Does Not Mean Identical

Different jurisdictions may legitimately have different:

- zoning systems;
- review processes;
- funding programs;
- local ordinances;
- project categories;
- reporting requirements.

The common structure should therefore preserve those differences rather than erase them.

A useful standard would define:

1. common core fields;
2. controlled definitions;
3. persistent identifiers;
4. provenance;
5. timestamps;
6. jurisdiction;
7. status/event history;
8. optional jurisdiction-specific fields.

This allows interoperability without pretending every local system is the same.

## Connection to the Housing Transmission Audit

The existing audit chain is:

**NEED → HOUSING GOALS / RHNA → LAND / ZONING CAPACITY → FEASIBLE PROJECT → FINANCING → APPROVAL → PERMIT → CONSTRUCTION → OCCUPANCY → AFFORDABILITY → RETENTION → STABILITY**

The data structure should allow a project to remain identifiable as it travels through that chain.

The important question becomes:

> **Can the same project be followed across the entire transmission pathway?**

If not, the missing identifier, field, definition, or interface becomes an identifiable data kink.

## Data Quality and Provenance

Every imported record should preserve:

- source agency;
- source system;
- source record identifier;
- date retrieved;
- reporting period;
- field definition;
- update timestamp;
- transformation performed by the conversion layer.

The Pure Data interface should never silently convert an unknown or estimated value into a fact.

The existing project evidence tags remain applicable:

- **KNOWN**
- **CALCULATED**
- **TESTED**
- **PROPOSED**
- **SPECULATIVE**
- **UNKNOWN**

## Government Data Is Not Automatically Public Data

Interoperability does not mean that every field should be publicly exposed.

The standard should distinguish between:

- public project-level information;
- restricted administrative information;
- personally identifiable information;
- confidential financial information;
- protected household information.

The Pure Data research interface should initially operate on appropriate public or synthetic project-level data.

## Relationship to Existing HCD Work

HCD already uses standardized reporting structures in several areas. Its housing data strategy specifically discusses improving data quality, changing submission formats, requiring unique project identifiers, and tracking projects through the development pipeline. citeturn0search12

HCD also requires standardized formats, forms, and definitions for the electronic Housing Element sites inventory. citeturn0search9

This suggests that the research should first investigate what standards and identifiers already exist before proposing a new one.

## Research Questions Before Any Government Request

1. What project identifiers already exist in Santa Cruz County?
2. What project identifiers already exist in the City of Santa Cruz?
3. Which identifiers appear in HCD reporting?
4. Can one project be matched across planning, permitting, financing, construction, and occupancy records?
5. Which fields already have standardized definitions?
6. Which fields are jurisdiction-specific?
7. Which records are machine-readable?
8. Which records have stable download/API mechanisms?
9. Where does the same project receive different identifiers?
10. Where do definitions change between systems?
11. Which stages lack a public project-level record?
12. What privacy restrictions affect cross-system linkage?

## Desired End State

The desired architecture is not:

**Government → Paul manually rebuilds data**

It is:

**Government Standard**
→ **portable project record**
→ **automatic validation**
→ **automatic conversion**
→ **Pure Data objects**
→ **interactive explanation / simulation**

And potentially:

**Government Standard**
→ **GIS / dashboard / database / research tool / other compatible application**

## First Practical Test

Do not begin with the entire California housing system.

Select a small number of real projects and test whether their records can be connected across stages.

For each project:

**PROJECT_ID**
→ planning
→ zoning
→ application
→ financing
→ approval
→ permit
→ construction
→ completion
→ occupancy
→ affordability / retention where documented.

Record every point where the identifier, definition, status, or data source changes.

That test will tell us whether the proposed common structure is actually useful.

## Principle

**The government should not have to use Pure Data.**

**Pure Data should be able to understand the government's standardized data.**

**And another tool should be able to understand the same data.**

That is the interoperability goal.
