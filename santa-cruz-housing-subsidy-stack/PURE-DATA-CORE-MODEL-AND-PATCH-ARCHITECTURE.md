# Pure Data Core Model and Patch Architecture

**Status:** RESEARCH / TECHNICAL REFERENCE

## 1. Patch as a directed system

A Pd patch is a directed visual network:

INPUT → OBJECT → OBJECT → OUTPUT

or:

INPUT → ROUTER → TRANSFORM → BRANCH → SUBPROCESS → MERGE → OUTPUT

This is relevant because housing delivery is also a directed process with branching paths, repeated reviews, parallel funding streams, and downstream outcomes.

## 2. Control flow and signal flow

Pd has a discrete message/control system and a continuous signal-processing system.

For housing, message/event processing is the more relevant layer. Examples:
- application submitted;
- review started;
- review completed;
- financing approved;
- permit issued;
- construction started;
- project completed;
- occupancy reached.

The signal system is not necessary for the first housing model.

## 3. Event model

A project can be represented by a persistent PROJECT_ID plus events such as:

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
- units;
- affordability;
- cost;
- notes;
- uncertainty.

This aligns closely with the project's proposed event-based housing record.

## 4. State model

Event history and current state should be separated.

**Event history:** what happened?

**Current state:** where is it now?

Example:

APPLICATION → UNDER_REVIEW

PERMIT → ISSUED

OCCUPANCY → OCCUPIED

This prevents a current label from replacing the historical path.

## 5. Inlets and outlets as interfaces

Pd objects have explicit interfaces. A housing abstraction could conceptually accept:
- project record;
- current status;
- financing state;
- review state.

It could output:
- next state;
- delay;
- friction;
- loss;
- completed units;
- unresolved condition.

This is a modeling analogy, not a claim that government software already has Pd-like interfaces.

## 6. Subpatches

A subpatch can hide a detailed process behind one visible component.

Example:

[FINANCING]

could contain:
- funding sources;
- eligibility;
- application;
- underwriting;
- subsidy;
- debt;
- closing;
- disbursement;
- conditions.

From a distance it is one box. At zoom level it becomes a process.

## 7. Abstractions

An abstraction is a reusable Pd patch that can be instantiated like an object.

Conceptually:

housing-project 101
housing-project 102
housing-project 103

could share one structural model while receiving different project records.

This supports a critical separation:

**MODEL = reusable structure**

**DATA = project-specific facts**

## 8. Graph-on-parent

Pd supports graph-on-parent interfaces, allowing selected GUI elements from a subpatch/abstraction to appear on the parent.

A housing stage could expose:
- current unit count;
- current status;
- elapsed days;
- funding amount;
- friction indicator;
- occupancy count.

The detailed process remains inside the component.

## 9. Arrays and tables

Arrays can represent numerical series:
- review days;
- development cost;
- planned units;
- occupied units;
- retained households.

These are displays/calculations, not evidence merely because Pd displays them.

## 10. Data structures

Pd data structures provide a more advanced representation system. Current Pd documentation describes improvements that make them more useful for messages/sequences and pointer traversal.

A future research prototype could investigate structured objects for:
- project;
- site;
- event;
- financing package;
- review event;
- permit;
- occupancy record.

This remains a prototype question.

## 11. Routing and branching

Pd routing can represent different project pathways:

PROJECT
→ market-rate
→ affordable
→ supportive
→ farmworker
→ ADU
→ rehabilitation
→ preservation

Financing can branch into:
→ local
→ state
→ federal
→ tax credit
→ private
→ mixed stack

The point is not to rank pathways. It is to expose their differences.

## 12. Feedback loops

Housing is not purely linear.

Examples:

REVIEW → REQUEST CHANGES → RESUBMIT → REVIEW

FINANCING CONDITION → REDESIGN → COST CHANGE → FINANCING REASSESSMENT

OCCUPANCY → MONITORING → PRESERVATION ACTION

Pd can display these loops explicitly.

## 13. Parallel paths

A project may move through several systems at once:

PLANNING
FINANCING
ENVIRONMENTAL
BUILDING
UTILITIES
AFFORDABILITY
SUPPORTIVE SERVICES
REPORTING

A patch can show parallel branches and where they reconnect.

That makes it useful for examining overlaps, underlaps, duplicated work, and missing handoffs.

## 14. Timing

Pd has timing objects and a real-time execution model.

A housing model could demonstrate:
- sequential delay;
- parallel delay;
- repeated review;
- queueing;
- waiting;
- deadlines;
- event ordering.

Always distinguish:
- observed duration;
- calculated duration;
- simulated duration.

A simulated 90-day review is not evidence that a real review takes 90 days.

## 15. Proposed housing object vocabulary

These are project names, not Pd-standard objects:

housing.project
housing.site
housing.need
housing.capacity
housing.zoning
housing.financing
housing.review
housing.permit
housing.construction
housing.occupancy
housing.affordability
housing.retention
housing.stability
housing.friction
housing.provenance

The first implementation should probably use ordinary abstractions rather than custom compiled objects.

## 16. Model/data/simulation separation

### MODEL
How the process is structured.

### DATA
What actually happened, with provenance.

### SIMULATION
What happens if inputs are changed.

A simulation result must never silently become a factual claim.

## 17. Evidence-preserving patch design

Imported data should retain:
- source system;
- source record ID;
- persistent project ID;
- source URL;
- reporting period;
- retrieval date;
- field definition;
- transformation history.

The project's evidence tags can remain visible:

KNOWN
CALCULATED
TESTED
PROPOSED
SPECULATIVE
UNKNOWN

## 18. Distance-to-detail architecture

### Level 0
NEED → PLAN → LAND → MONEY → PERMISSION → BUILD → HOME → PERSON

### Level 1
NEED → RHNA/GOAL → CAPACITY → PROJECT → FINANCING → APPROVAL → PERMIT → CONSTRUCTION → OCCUPANCY → AFFORDABILITY → RETENTION → STABILITY

### Level 2
Open one stage and expose the actual process.

### Level 3
Show agency records, definitions, dates, and evidence.

### Level 4
Show source documents and data definitions.

This is the technical form of the project's "zoom quill" idea.

## Conclusion

Pd's most relevant feature is not sophisticated audio.

It is that a patch can make **relationships executable and visible at the same time**.

That is a strong conceptual match for a project whose central problem is the relationship among many facts and systems.

## References

- https://github.com/pure-data/pure-data
- https://msp.ucsd.edu/Pd_documentation/
- https://msp.ucsd.edu/Pd_documentation/5.current.status.htm
