# Pure Data Network, Data, and Interoperability Research

**Status:** RESEARCH / TECHNICAL REFERENCE

## Central question

The project has moved from:

"Can Pure Data draw the housing system?"

to:

"Can a standardized machine-readable housing record be converted into a Pure Data representation without losing meaning?"

That is the more important question.

## Proposed interoperability chain

GOVERNMENT SYSTEMS
↓
STANDARDIZED PROJECT RECORDS
↓
COMMON DATA CONTRACT
↓
VALIDATION
↓
CONVERSION / CROSSWALK
↓
PURE DATA OBJECT GRAPH
↓
VISUAL EXPLANATION / SIMULATION

The same data should also be usable by GIS, spreadsheets, databases, dashboards, statistical tools, and future interfaces.

## Persistent identifiers

A project can appear in:
- planning;
- permitting;
- financing;
- construction;
- affordable-housing monitoring;
- occupancy/completion systems.

If each system uses unrelated identifiers, the project history becomes difficult to reconstruct.

California HCD's data-strategy work has specifically discussed tracking the housing development pipeline from initial application through occupancy and the use of unique identifiers so projects can be mapped and tracked through the full process.

Therefore the persistent identifier is more fundamental than the Pd interface.

## Event model

A project can be represented as PROJECT_ID plus events:

APPLICATION
REVIEW
FINANCING
ENTITLEMENT
PERMIT
CONSTRUCTION_START
INSPECTION
COMPLETION
OCCUPANCY
AFFORDABILITY
RETENTION

Each event can carry:
- timestamp;
- agency/system;
- status;
- source record;
- unit count;
- affordability;
- cost;
- notes;
- uncertainty.

The dates in a prototype must be clearly identified as actual, calculated, or synthetic.

## State model

Separate:

**EVENT HISTORY = what happened**

from:

**CURRENT STATE = where the project is now**

This prevents a current status label from replacing the historical record.

## Provenance

A value should ideally retain:

FIELD
→ value
→ source agency
→ source system
→ source record ID
→ retrieval date
→ reporting period
→ field definition
→ transformation

This is essential when County, City, State, federal, and other sources are combined.

## Transformations

A conversion layer may need to perform:
- type conversion;
- date normalization;
- controlled-vocabulary mapping;
- jurisdiction mapping;
- status mapping;
- identifier matching;
- missing-value handling;
- duplicate detection;
- provenance preservation.

Every transformation should be documented.

## Example conversion

Government record:

PROJECT_ID = SC-000123
UNIT_COUNT = 48
CURRENT_STATUS = Permit Issued
PERMIT_DATE = 2026-07-14

Pd representation:

PROJECT 123
UNITS 48
STATE PERMITTED
PERMIT_DATE 2026-07-14

The critical rule is that "permit issued" must not become "constructed" merely because the visualization has a BUILD box.

## Data sensitivity

Machine-readable does not mean public-by-default.

Possible classifications:

### Public
Project ID, general location, unit count, project type, public milestones.

### Restricted administrative
Internal workflow IDs, staff notes, security information.

### Financially sensitive
Confidential underwriting or proprietary terms.

### Personal
Household names, contact information, protected eligibility information.

The Pd prototype should use public or synthetic project-level data.

## Network communication

Pd can communicate over networks through built-in mechanisms and external libraries.

Relevant technologies include:
- UDP;
- TCP;
- OSC;
- FUDI/Pd messaging;
- serial communication;
- application bridges.

A preferred future architecture is:

DATABASE / OFFICIAL DATA
↔ DATA SERVICE
↔ CONVERSION LAYER
↔ Pd

rather than placing the authoritative database inside a patch.

## OSC is transport, not the complete data standard

An OSC message can transport a value, but it does not by itself define:
- the meaning of the value;
- the source;
- the time basis;
- whether it is current;
- correction rules;
- privacy classification.

Therefore:

**DATA MODEL FIRST**

**TRANSPORT SECOND**

## File exchange versus API

Both should be investigated.

### File exchange
CSV, JSON, GeoJSON, Parquet, or another documented format.

Advantages:
- archivable;
- inspectable;
- versionable;
- easy to test.

### API
Advantages:
- automated retrieval;
- current data;
- machine-to-machine exchange.

A mature system could provide both downloadable historical snapshots and a current API.

## Data versioning

The schema itself changes. Records should therefore identify:
- schema version;
- source version where applicable;
- reporting period;
- update time.

## Missing and conflicting data

Do not turn missing information into zero.

Possible states:
- known;
- unknown;
- not applicable;
- withheld;
- estimated;
- calculated;
- conflicting;
- stale.

A Pd patch can make these states visible.

## Cross-system matching test

Select a small number of real public housing projects and attempt to match them across:
- County planning;
- County permitting;
- City planning where applicable;
- HCD reporting;
- local financing;
- affordable-housing monitoring;
- completion/occupancy information where public.

Record:
- project-name differences;
- unit-count differences;
- date differences;
- status differences;
- missing IDs;
- duplicate records;
- parcel/phase mismatches.

The mismatches are findings, not merely cleanup problems.

## Pd as an audit instrument

The patch can expose data problems.

Example:

PROJECT → missing permit date → UNKNOWN

PROJECT → two unit counts disagree → CONFLICT

PROJECT → permitted status plus later construction event → both events remain visible

This makes the patch a potential audit instrument rather than only a visualization.

## Tablecloth-fold model

The project already treats each system layer as a tablecloth that can fold at interfaces.

Data can fold when a field changes:
- name;
- definition;
- time basis;
- jurisdiction;
- unit;
- eligibility;
- status;
- responsible agency.

The conversion layer should expose these folds rather than flatten them.

## Conceptual minimum project record

- PROJECT_ID
- SITE_ID
- APN_OR_SITE_REFERENCE
- JURISDICTION
- PROJECT_NAME
- PROJECT_TYPE
- UNIT_COUNT
- AFFORDABILITY_CATEGORY
- APPLICATION_DATE
- ENTITLEMENT_DATE
- FINANCING_STATUS
- PERMIT_DATE
- CONSTRUCTION_START
- COMPLETION_DATE
- OCCUPANCY_DATE
- CURRENT_STATUS
- SOURCE_SYSTEM
- SOURCE_RECORD_ID
- SOURCE_UPDATED_AT
- SCHEMA_VERSION

This is a research field list, not a proposed final government standard.

## Desired architecture

AUTHORITATIVE SOURCE
↓
STANDARD PROJECT RECORD
↓
VALIDATOR
↓
CROSSWALK / CONVERSION
↓
Pd OBJECT GRAPH
↓
VISUALIZATION
↓
SIMULATION

The same standard can branch to GIS, database, spreadsheet, dashboard, research program, and Pure Data.

## Conclusion

The important technology question is not whether Pd can process housing data.

The harder question is whether housing data can be defined well enough that Pd, GIS, databases, dashboards, and future tools can all consume the same underlying record without silently changing its meaning.

That is the interoperability question.

## References

- California HCD data-strategy materials on housing-development pipeline tracking and unique identifiers.
- Pure Data: https://github.com/pure-data/pure-data
- Deken: https://deken.puredata.info/
- IEM Pd distribution: https://github.com/iem-projects/pd-iem
- IEM network tools: https://github.com/umlaeute/pd-iemnet
- libpd: https://github.com/libpd/libpd
