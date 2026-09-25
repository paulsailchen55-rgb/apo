# Pure Data Housing Transmission Interface

## Status

**PROPOSED / EXPLORATORY**

This is a possible technical interface for the Santa Cruz Housing Subsidy Stack research.

It is not a replacement for the existing research model, and it is not yet a claim that Pure Data is the final implementation platform.

## The Idea

The housing system is becoming difficult to understand because it is not one process.

It is a stack of interacting systems:

**NEED → PLAN → LAND → MONEY → PERMISSION → BUILD → HOME → PERSON**

Behind each simple word are many agencies, programs, eligibility rules, funding sources, measurements, reporting systems, timing requirements, and definitions.

The proposed interface would let a person see the simple picture first and then **zoom into the machinery behind each part**.

One possible way to prototype that is **Pure Data (Pd)**.

Pure Data is a visual dataflow programming environment in which objects are connected to pass data and messages through a patch. It was originally used for real-time music and multimedia, but the same dataflow idea could be used experimentally to represent a housing-transmission system.

## Why Pure Data Fits the Concept

The important feature is not music or video.

The important feature is the **patch**.

A housing pathway could be represented as connected blocks:

**NEED**
↓
**HOUSING GOAL / RHNA**
↓
**LAND / ZONING**
↓
**FEASIBLE PROJECT**
↓
**FINANCING**
↓
**APPROVAL**
↓
**PERMIT**
↓
**CONSTRUCTION**
↓
**OCCUPANCY**
↓
**AFFORDABILITY**
↓
**RETENTION**
↓
**STABILITY**

Each block could contain more detail.

A person could start at the distance view and then open a block to see the underlying agencies, programs, definitions, records, time, money, and eligibility conditions.

That corresponds closely to the project's existing principle:

> **The final explanation should be understandable from a distance and explorable in detail.**

## Simulation Rather Than Just a Diagram

The more interesting possibility is that this would not merely be a picture.

The patch could become an experimental model.

A user could change a condition and observe how the pathway changes.

For example, a prototype could allow a user to change:

- number of planned units;
- zoning capacity;
- financing availability;
- review time;
- number of review cycles;
- development cost;
- subsidy amount;
- construction duration;
- lease-up duration;
- affordability requirements;
- project attrition;
- occupancy;
- retention.

The output could then show how much capacity survives each transmission point.

For example:

**1,000 planned units**

→ 900 feasible

→ 850 financed

→ 820 approved

→ 800 permitted

→ 760 constructed

→ 720 occupied

→ 500 affordable

→ 470 retained

→ 450 stable households

These numbers would be **model inputs**, not claims about the real County or City.

The real research data would be inserted only when documented.

## The Kink-Point Model

This could provide a visual implementation of the project's existing "Tablecloth Fold" / kink-point idea.

At every connection, the patch could ask:

**What changed here?**

Possible variables include:

- capacity;
- time;
- money;
- eligibility;
- definition;
- responsibility;
- information;
- reporting;
- project status.

A visible change would not automatically mean failure.

The patch would simply expose the transition so the researcher can ask why it changed.

That preserves the project's existing rule:

> **A kink is not automatically a policy failure. The interface must identify the transition first and determine its effect second.**

## Fractal / Zoom Interface

The larger idea is a **zoomable housing system**.

At the outer level:

**NEED → PLAN → LAND → MONEY → PERMISSION → BUILD → HOME → PERSON**

Zoom into **MONEY**:

**MONEY**
→ federal programs
→ state programs
→ local funds
→ tax credits
→ loans
→ grants
→ project financing
→ conditions
→ reporting

Zoom into one of those:

**LOCAL HOUSING FUND**
→ eligibility
→ application
→ underwriting
→ award
→ agreement
→ construction
→ completion
→ occupancy
→ reporting

The same principle can continue inward.

This is why the idea resembles a fractal interface: the user does not have to display every layer at once, but every layer remains available.

## Simulation Rules

The eventual prototype should distinguish between:

**KNOWN**
- directly documented real-world information.

**CALCULATED**
- derived from documented information.

**TESTED**
- independently checked or reproduced.

**PROPOSED**
- a suggested model or interface behavior.

**SPECULATIVE**
- a hypothesis or experimental assumption.

**UNKNOWN**
- not yet established.

The simulator must never make a simulated number look like an official County, City, State, or federal measurement.

## Two Modes

### 1. Explain Mode

The user follows the system as a map.

The objective is comprehension.

**What happens to a housing unit as it travels through the system?**

### 2. Experiment Mode

The user changes conditions.

The objective is understanding transmission.

**What happens if this variable changes?**

The experiment should show the resulting pathway without presenting the result as a prediction of what government will do.

## Relationship to the Housing Transmission Audit

The Pure Data idea should sit **on top of** the existing research rather than replace it.

The research remains:

**NEED → HOUSING GOALS / RHNA → LAND / ZONING CAPACITY → FEASIBLE PROJECT → FINANCING → APPROVAL → PERMIT → CONSTRUCTION → OCCUPANCY → AFFORDABILITY → RETENTION → STABILITY**

Pure Data would potentially become a visualization and experimentation layer for that chain.

The evidence remains in the Markdown research files.

The patch becomes an interface to the model.

## Important Restraint

This is a technological direction, not an instruction to build the entire system immediately.

The current priority remains:

**Map the existing system first.**

The Pure Data prototype can begin with a deliberately small model:

**10–12 boxes, a few adjustable variables, and visible transmission losses.**

If that simple model proves useful, it can be expanded.

If it does not, the research does not depend on it.

## First Prototype

A first patch could contain only:

1. Need
2. RHNA / housing goal
3. Zoning capacity
4. Feasible project
5. Financing
6. Approval
7. Permit
8. Construction
9. Occupancy
10. Affordability
11. Retention
12. Stability

Each stage would pass a simple value representing housing capacity.

A control could change one variable at a time.

The display would show:

**INPUT → TRANSMISSION → OUTPUT**

and identify where the value changed.

That would be enough to test the concept without building the entire housing system.

## Why This May Matter

The underlying housing system may never become simple.

The interface can become simpler without pretending the system itself is simple.

That is the key distinction.

The goal is not:

> **Make the housing system simple.**

The goal is:

> **Make the housing system navigable.**

Pure Data may provide a practical experimental environment for testing that idea because its visual dataflow model makes the relationships between inputs, transformations, and outputs explicit.

## Research Boundary

This file does not establish that Pure Data is suitable for a production government interface.

It establishes only a **PROPOSED research experiment**:

> Can a visual dataflow patch make a complex housing-transmission system understandable from a distance, while allowing the user to zoom into the details and change selected variables to observe different simulated outcomes?

That question can be tested without deciding the final technology.

## Principle

**Simple from a distance.**

**Detailed when you zoom.**

**Interactive when you experiment.**

**Evidence-bound at every layer.**

**Never confuse the model with the real world.**
