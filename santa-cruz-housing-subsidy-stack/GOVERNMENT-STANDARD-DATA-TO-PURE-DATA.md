# GOVERNMENT-STANDARD-DATA-TO-PURE-DATA.md

**Status:** PROPOSED / RESEARCH DIRECTION  
**Project family:** Housing Transmission Audit / Standardized Machine-Readable Housing Project Data / Pure Data Interface  
**Relationship:** Complementary to `STANDARDIZED-MACHINE-READABLE-HOUSING-PROJECT-DATA.md`

---

## 1. Purpose

This document takes the next step after defining a possible government-standard housing data structure.

The question is:

> **If government agencies publish standardized, machine-readable housing-project data, how can that data be brought into Pure Data without losing identifiers, relationships, provenance, status, dates, uncertainty, or the distinction between observed data and simulation?**

The goal is **not** to make government use Pure Data.

The goal is:

> **Government produces understandable standard data. Pure Data can understand that data. Other tools can understand the same data.**

This creates a conversion layer rather than making Pure Data the government database.

---

## 2. The Architecture

The proposed architecture is:

```
GOVERNMENT SYSTEMS
        ↓
GOVERNMENT STANDARD DATA
        ↓
VALIDATION
        ↓
CONVERSION / MAPPING
        ↓
PORTABLE PROJECT RECORD
        ↓
PURE DATA OBJECTS
        ↓
PURE DATA PATCH
        ↓
VISUALIZATION / AUDIT / EXPERIMENT
        ↓
HUMAN
```

The same standardized source should also be able to travel to:

```
GOVERNMENT STANDARD DATA
   ├──→ GIS
   ├──→ DATABASE
   ├──→ SPREADSHEET
   ├──→ DASHBOARD
   ├──→ RESEARCH TOOL
   ├──→ PURE DATA
   └──→ OTHER FUTURE INTERFACES
```

Pure Data is therefore **one consumer of the standard**, not the owner of the standard.

---

## 3. Why This Is Not Just a File-Import Problem

A housing project is not merely a row of numbers.

A project may appear in multiple systems:

- Housing Element
- Sites Inventory
- RHNA reporting
- zoning
- planning applications
- entitlement
- financing
- building permits
- inspections
- construction
- completion
- occupancy
- affordability monitoring
- preservation
- supportive housing
- homelessness or rehousing systems

The same project may have:

- different names;
- different identifiers;
- different dates;
- different definitions;
- different status labels;
- different unit counts at different stages;
- different reporting periods.

Therefore the conversion layer must preserve **relationships**, not merely values.

---

## 4. Minimum Portable Project Record

A proposed minimum record is:

```
PROJECT_ID
SITE_ID
JURISDICTION
PROJECT_NAME
PROJECT_TYPE

UNIT_COUNT
AFFORDABILITY
TENURE

EVENT
EVENT_DATE
STATUS

SOURCE_SYSTEM
SOURCE_RECORD_ID
SOURCE_DOCUMENT
SOURCE_LOCATION

REPORTING_PERIOD
LAST_UPDATED

PROVENANCE
DEFINITION_VERSION

RELATED_PROJECT_ID
RELATED_SITE_ID
RELATED_EVENT_ID
```

This is deliberately small.

The first experiment should determine which fields are actually necessary before creating a large universal schema.

---

## 5. Event-Based Model

The project should not be represented only as a single current status.

A more useful model is an event history:

```
PROJECT_ID
    ↓
APPLICATION
    ↓
REVIEW
    ↓
ENTITLEMENT
    ↓
FINANCING
    ↓
APPROVAL
    ↓
PERMIT
    ↓
CONSTRUCTION
    ↓
COMPLETION
    ↓
OCCUPANCY
    ↓
AFFORDABILITY
    ↓
RETENTION
```

Each event can carry:

```
EVENT_ID
PROJECT_ID
EVENT_TYPE
EVENT_DATE
STATUS
SOURCE
SOURCE_RECORD_ID
SOURCE_LOCATION
UNIT_COUNT
AFFORDABILITY
NOTES
PROVENANCE
```

This allows Pure Data to represent the housing process as a changing dataflow rather than as one static table.

---

## 6. The Conversion Layer

The conversion layer is the critical boundary.

It should perform at least five operations:

### 6.1 Validate

Check that required fields exist and that values conform to the published standard.

### 6.2 Map

Translate government field names into the common internal vocabulary.

Example:

```
"projectNumber"
        ↓
PROJECT_ID
```

or:

```
"unitsProposed"
        ↓
UNIT_COUNT
```

The mapping must be documented.

### 6.3 Preserve

Do not discard:

- original identifier;
- original field name;
- source system;
- source document;
- reporting period;
- timestamp;
- definition;
- uncertainty;
- transformation history.

### 6.4 Convert

Transform the validated record into a Pure Data-readable representation.

### 6.5 Reconstruct

Allow the Pure Data representation to point back to the source record and original evidence.

The conversion should therefore be reversible at the level of meaning, even if the file format changes.

---

## 7. Pure Data Representation

Pure Data has several native mechanisms that could represent the converted information.

The research should test:

- messages and lists for small event records;
- `[text]` for tabular/event data;
- arrays for numerical sequences;
- data structures for linked visual records;
- abstractions for reusable housing-system components;
- subpatches for stages of the transmission chain.

Pd's own documentation describes data structures with fields such as floats, symbols, text, and arrays, while arrays provide a way to store and access sequences of values. These are possible implementation mechanisms, not evidence that Pd is already a housing-data standard.

Source: Pure Data manual and source documentation.

---

## 8. Proposed Pure Data Object Vocabulary

A first housing-data abstraction layer could use objects conceptually named:

```
[project]
[site]
[event]
[status]
[units]
[affordability]
[financing]
[permit]
[construction]
[occupancy]
[retention]
[source]
[provenance]
[relationship]
```

These names are **proposed vocabulary**, not existing Pure Data objects.

They could eventually be implemented as abstractions.

For example:

```
[project PROJECT-001]
        |
        +---- [site SITE-001]
        |
        +---- [event application 2026-03-10]
        |
        +---- [event permit 2026-08-22]
        |
        +---- [units 100]
        |
        +---- [affordability 80 affordable]
```

The visual patch would therefore expose the relationships contained in the source data.

---

## 9. One Project, Many Records

A critical test is whether records from different government systems can converge on one project.

Example:

```
County Planning Record
        PROJECT_ID = COUNTY-123
                ↓
County Permit Record
        PERMIT_ID = P-456
                ↓
HCD APR Record
        PROJECT_ID = HCD-789
                ↓
Financing Record
        PROJECT_ID = FUND-321
```

The conversion layer should be able to express:

```
COUNTY-123
    ↕
HCD-789
    ↕
FUND-321
    ↕
P-456
```

without pretending that these identifiers are identical.

The relationship itself becomes data.

---

## 10. Relationship Objects

This may be more important than the individual fields.

A proposed relationship record:

```
RELATIONSHIP_ID
FROM_ID
FROM_TYPE
TO_ID
TO_TYPE
RELATIONSHIP_TYPE
SOURCE
CONFIDENCE
DATE_ESTABLISHED
PROVENANCE
```

Possible relationship types:

- SAME_PROJECT_AS
- SAME_SITE_AS
- DERIVED_FROM
- REPORTED_IN
- FINANCED_BY
- PERMITTED_BY
- REPLACED_BY
- PHASE_OF
- RELATED_TO
- SUPERSEDES
- UNKNOWN_RELATIONSHIP

A relationship should never be silently invented because two names look similar.

---

## 11. The Tablecloth-Fold Model in Pure Data

The existing Housing Transmission Audit describes a chain:

```
NEED
→ HOUSING GOAL / RHNA
→ LAND / ZONING
→ FEASIBLE PROJECT
→ FINANCING
→ APPROVAL
→ PERMIT
→ CONSTRUCTION
→ OCCUPANCY
→ AFFORDABILITY
→ RETENTION
→ STABILITY
```

Pure Data can make each transition visible.

For example:

```
[RHNA]
   |
   v
[SITES]
   |
   v
[PROJECT]
   |
   v
[FINANCING]
   |
   v
[APPROVAL]
   |
   v
[PERMIT]
   |
   v
[BUILD]
   |
   v
[OCCUPANCY]
```

A user could click or zoom into a transition.

The important question becomes:

> **What record proves that this connection exists?**

That question keeps the visual model tied to evidence.

---

## 12. Observed Data vs. Calculated Data vs. Simulation

Pure Data can calculate things.

That creates a major evidence boundary.

Every value should be identifiable as one of:

```
KNOWN
CALCULATED
TESTED
PROPOSED
SPECULATIVE
UNKNOWN
```

Example:

```
KNOWN:
County reports 100 proposed units.

CALCULATED:
100 proposed - 20 removed = 80 remaining.

TESTED:
Conversion correctly imports the 100-unit record.

PROPOSED:
Model assumes 10% construction loss.

SPECULATIVE:
Simulation produces 72 completed units under that assumption.

UNKNOWN:
Actual occupancy date not located.
```

A simulation result must never silently become an observed government fact.

---

## 13. Pure Data as Audit Instrument

The patch could have separate modes.

### EXPLAIN MODE

Shows the documented system.

### AUDIT MODE

Shows where records, definitions, dates, or identifiers change.

### EXPERIMENT MODE

Allows hypothetical variables to change.

### TRACE MODE

Shows the evidence path from a displayed value back to the source record.

### BROADEN MODE

Shows related records that were not selected by the current view.

This connects directly to the Selective Librarian work.

The librarian finds relevant records.

Pure Data can then make their relationships visible.

---

## 14. Example: Unit Count Changes

Suppose a project appears as:

```
Housing Element: 120 units
Application:       110 units
Entitlement:       105 units
Permit:             98 units
Construction:       98 units
Occupancy:          96 units
```

Pure Data should not simply display:

```
96 units
```

It should be capable of showing:

```
120
 ↓ -10
110
 ↓ -5
105
 ↓ -7
98
 ↓ 0
98
 ↓ -2
96
```

Then:

> **Why did the number change?**

becomes a research question.

The patch should point toward the records that document each transition.

It should not invent the explanation.

---

## 15. Example: Affordability Changes

The same project may have different affordability descriptions at different stages.

The system should preserve:

```
AFFORDABILITY_STATUS
AFFORDABILITY_DEFINITION
AFFORDABILITY_SOURCE
AFFORDABILITY_DATE
AFFORDABILITY_UNIT_COUNT
AFFORDABILITY_INCOME_LEVEL
AFFORDABILITY_RESTRICTION
```

This matters because:

```
"affordable"
```

is not necessarily one universal data value.

The standard must preserve the definition attached to the term.

---

## 16. Source Provenance Inside the Patch

A visible value should be traceable.

For example:

```
[units 98]
    |
    +--> SOURCE: County permit record
    +--> RECORD_ID: P-456
    +--> DATE: 2026-08-22
    +--> LOCATION: document/page/section
    +--> STATUS: permitted
```

The patch should not require the user to trust the visualization.

The visualization should provide a route back to evidence.

---

## 17. Machine-Readable Does Not Mean Machine-Only

The standard should support both:

### Human-readable

- readable field names;
- definitions;
- documentation;
- source descriptions;
- understandable status labels;
- accessible original documents.

### Machine-readable

- stable identifiers;
- controlled values;
- timestamps;
- structured relationships;
- explicit definitions;
- versioning;
- provenance;
- machine-readable files.

The machine-readable representation should be an additional layer, not a replacement for the human-readable record.

---

## 18. Existing California Direction

This concept has a strong connection to existing HCD data work.

HCD's housing data strategy explicitly recommends tracking the development pipeline from initial application through occupancy and using unique project identifiers so projects can be mapped and followed through the development process. HCD also identifies inconsistent local reporting and project tracking as data-quality problems. citeturn0search16

HCD currently provides Annual Progress Report forms and downloadable APR data, including CSV data through California Open Data. HCD Connect is used for Housing Elements, Sites Inventories, and APR submissions. citeturn0search4turn0search10

This means the proposed project is not starting from the assumption that government has no data standard.

The research question is narrower:

> **How far can existing or emerging government-standard data travel through a common conversion layer without losing meaning?**

---

## 19. First Real Test

Do not begin by designing the complete standard.

Begin with a small test.

Select:

- one Santa Cruz County housing project;
- one City of Santa Cruz housing project;
- a small number of records for each.

For each project, attempt to build:

```
PROJECT_ID
→ SITE_ID
→ APPLICATION
→ ENTITLEMENT
→ FINANCING
→ PERMIT
→ CONSTRUCTION
→ OCCUPANCY
→ AFFORDABILITY
→ STABILITY
```

Then record:

| Stage | Source | Identifier | Date | Status | Units | Definition | Forward Connection |
|---|---|---|---|---|---:|---|---|
| Application | TBD | TBD | TBD | TBD | TBD | TBD | Entitlement |
| Entitlement | TBD | TBD | TBD | TBD | TBD | TBD | Permit |
| Financing | TBD | TBD | TBD | TBD | TBD | TBD | Construction |
| Permit | TBD | TBD | TBD | TBD | TBD | TBD | Construction |
| Construction | TBD | TBD | TBD | TBD | TBD | TBD | Occupancy |
| Occupancy | TBD | TBD | TBD | TBD | TBD | TBD | Affordability |
| Affordability | TBD | TBD | TBD | TBD | TBD | TBD | Retention |
| Stability | TBD | TBD | TBD | TBD | TBD | TBD | TBD |

Do not fill unknown fields by inference.

---

## 20. First Pure Data Prototype

The first prototype should be extremely small.

### Input

One standardized project record.

### Conversion

```
standard record
      ↓
field validation
      ↓
field mapping
      ↓
event objects
      ↓
relationship objects
```

### Patch

Approximately:

```
[PROJECT]
   |
[SITE]
   |
[EVENTS]
   |
[RELATIONSHIPS]
   |
[STATUS]
   |
[SOURCE]
```

### Output

A visual project timeline or transmission chain.

The prototype succeeds if a human can answer:

1. What is this project?
2. What happened to it?
3. What changed?
4. Where did the information come from?
5. What is known versus calculated?
6. What record should I inspect next?

---

## 21. What the Standard Must Not Do

The standard should not:

- force every jurisdiction to use the same internal software;
- erase jurisdiction-specific fields;
- collapse different definitions into one label;
- replace source documents;
- expose protected household information;
- create a single centralized database by default;
- assume every project has the same lifecycle;
- treat missing data as zero;
- treat proposed units as built units;
- treat built units as occupied units;
- treat occupied units as stable households;
- turn simulations into forecasts;
- hide transformations.

---

## 22. Privacy Boundary

Project-level interoperability and household-level interoperability are different problems.

A public project record may contain:

- project name;
- location;
- unit counts;
- dates;
- permits;
- public financing;
- affordability categories.

Household systems may contain protected or sensitive information.

The Pure Data prototype should therefore use:

- public project-level records;
- synthetic data;
- or appropriately de-identified data.

The existence of a common standard does not imply that every field should be publicly accessible.

---

## 23. Interoperability Principle

The central principle is:

> **Standardize meaning before standardizing software.**

And:

> **Standardize the record before standardizing the interface.**

Then:

```
STANDARD DATA
     ↓
MANY POSSIBLE INTERFACES
     ↓
GIS / DATABASE / DASHBOARD / PURE DATA / AI
```

This prevents the interface from becoming the data standard.

---

## 24. Relationship to the Selective Librarian

The Selective Librarian answers:

> **Which records and sections are relevant to this person's question?**

The standardized data layer answers:

> **What does each record mean, and how does it relate to other records?**

Pure Data answers:

> **How can those relationships be made visible and explored?**

Therefore:

```
OPEN PUBLIC RECORD
        ↓
DURABLE ARCHIVE
        ↓
STANDARDIZED DATA
        ↓
SELECTIVE LIBRARIAN
        ↓
RELATIONAL HIGHLIGHTING
        ↓
PURE DATA / GIS / OTHER TOOLS
        ↓
HUMAN
```

These are separate layers.

They should not be collapsed into one giant AI system.

---

## 25. Hard Question

The difficult question is not:

> Can Pure Data read a government file?

It almost certainly can be made to read some structured representation.

The harder question is:

> **Can the government data standard preserve enough meaning and relationship information that another tool can reconstruct the housing process without having to guess?**

That is the real test.

---

## 26. Design Rule

> **Do not design the Pure Data patch first. Design the portable record first.**

Then test whether the record can become a useful patch.

If it cannot, the problem may be in the data structure rather than in Pure Data.

---

## 27. Evidence Status

- **KNOWN:** HCD has existing housing data systems, APR structures, HCD Connect, Sites Inventory standards, and public APR data. citeturn0search4turn0search10
- **KNOWN:** HCD's data strategy recommends unique project identifiers and tracking projects through the development pipeline to occupancy. citeturn0search16
- **KNOWN:** Pure Data supports structured data mechanisms including data structures and arrays. citeturn1search0turn1search1
- **PROPOSED:** A portable housing-project record with persistent identifiers, events, relationships, provenance, and definitions.
- **PROPOSED:** A conversion layer from government-standard data into Pure Data objects.
- **PROPOSED:** Trace, audit, explain, and experiment modes.
- **TESTED:** Not yet tested against a real County/City project.
- **UNKNOWN:** Whether existing Santa Cruz County and City systems can already be mapped into one common project/event/relationship structure without substantial manual reconciliation.
- **UNKNOWN:** Which Pure Data representation will be most portable for the final prototype.

---

## 28. Next Research Step

The next step is **not another abstract schema**.

It is:

> **Take one real housing project and try to convert its actual public records into the proposed portable record.**

Record every place where the conversion fails.

Those failures become requirements for the standard.

That gives us:

```
REAL GOVERNMENT RECORDS
        ↓
ATTEMPTED STANDARDIZATION
        ↓
IDENTIFIED KINKS
        ↓
REVISED DATA STANDARD
        ↓
PURE DATA CONVERSION
        ↓
WORKING PROTOTYPE
```

This is the data equivalent of the Housing Transmission Audit:

> **Do not assume the transmission works. Put something through it and see where the signal changes.**
