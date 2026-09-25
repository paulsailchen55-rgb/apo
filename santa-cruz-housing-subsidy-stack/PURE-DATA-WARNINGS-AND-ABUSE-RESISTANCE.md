# Pure Data Warnings and Abuse-Resistance

**Status:** WARNING / DESIGN REQUIREMENT  
**Project relationship:** Pure Data Housing Transmission Interface  
**Research date:** 2026-09-25

## Why this file exists

A visual, executable dataflow system is not inherently benevolent.

The same capabilities that make Pure Data interesting for explaining a housing system can also make a system easier to optimize for harmful objectives, automate decisions that should remain accountable to people, conceal coercive rules inside a visual interface, centralize surveillance, rank or exclude people, manipulate access to housing or services, create feedback loops that reinforce an existing inequality, or turn uncertain data into apparently precise outputs.

Therefore this project must study **how the interface could be abused**, not only how it could be useful.

This is a design warning, not a claim that Pure Data itself is harmful.

## The central warning

> **A transparent diagram can make a harmful system easier to operate.**

Making a process visible is valuable. Making it executable can make it more powerful.

The project therefore must distinguish:

**UNDERSTANDING A SYSTEM**

from:

**OPTIMIZING A SYSTEM**

and from:

**AUTOMATING A DECISION**

Those are different activities.

## How the housing interface could be misused

### 1. Surveillance

A project that links planning, permitting, financing, occupancy, affordability, services, and household information could become a surveillance architecture if it combines more personal information than necessary.

Protection: use project-level data whenever possible; separate household identity from project/process data; minimize collection; document retention and deletion rules; do not put personal data into the prototype merely because the system can accept it.

### 2. Automated exclusion

A patch could calculate eligibility or route people toward different outcomes. A simple ACCEPT / REJECT flow can make a complex human decision look like a technical switch.

Protection: do not convert the research visualization into an eligibility authority; expose the rule and its legal/policy source; preserve human review where required; distinguish administrative assistance from automated determination.

### 3. Optimization of displacement

A model could optimize land value, redevelopment speed, unit production, cost reduction, vacancy reduction, or revenue. If displacement, preservation, household continuity, accessibility, or dignity are omitted from the objective function, the model may produce a numerically successful but socially harmful result.

Protection: never define success using only one metric. Keep occupancy, affordability, retention, preservation, accessibility, and stability visible.

### 4. Coercive routing

A visual system could route a person toward a predetermined program while hiding alternatives.

Protection: show available pathways; show uncertainty and missing information; do not present one pathway as inevitable when alternatives exist; allow escape and feedback paths; preserve the ability to challenge an incorrect record.

### 5. False precision

A patch can display exact numbers even when the underlying data are uncertain. A value such as REVIEW_TIME = 47 DAYS may look authoritative even if it was estimated from incomplete records.

Protection: distinguish KNOWN, CALCULATED, TESTED, PROPOSED, SPECULATIVE, and UNKNOWN. Also distinguish observed, reported, calculated, estimated, and simulated values.

A simulated output must never be silently presented as an observed fact.

### 6. Hidden policy inside the patch

A visual object can look neutral while containing a policy choice. An eligibility rule is not merely a technical operation; it embodies a definition.

Protection: expose policy rules; identify their source; record effective dates; distinguish law, regulation, agency policy, local procedure, and experimental assumptions; do not bury important policy decisions inside opaque abstractions.

### 7. Feedback-loop harm

A dataflow model can create reinforcing loops. For example: LOW ACCESS → FEWER APPLICATIONS → LOWER OBSERVED DEMAND → LOWER RESOURCE ALLOCATION → LOWER ACCESS.

If a system interprets its own reduced output as evidence that less service is needed, the model can reproduce the problem it measures.

Protection: inspect feedback loops explicitly; distinguish demand from observed participation; record missing or unreachable populations; test alternative explanations.

### 8. Gaming the metric

Once a metric becomes a target, organizations may optimize the metric instead of the underlying outcome.

PERMITS ISSUED ↑ does not necessarily mean OCCUPIED STABLE HOMES ↑.

The transmission chain exists partly to prevent this collapse:

NEED → PLAN → LAND → MONEY → PERMISSION → BUILD → HOME → PERSON → STABILITY

### 9. Centralization risk

A universal dataflow interface could become an attractive place to centralize many datasets. That can create a single point of surveillance, failure, institutional power, or difficult-to-audit transformation.

Protection: favor interoperable records over unnecessary centralization; maintain source provenance; preserve independent source systems; make transformations inspectable.

### 10. Malicious or untrusted dependencies

Pd supports extensions and libraries. Community documentation shows that libraries can create version, namespace, path, architecture, and maintenance problems; historical libraries may also be abandoned. Explicit library namespaces can reduce ambiguity. citeturn0search0turn0search1turn0search9

Therefore a patch should not be trusted merely because it opens successfully.

For research reproducibility: record Pd version; record every external/library; record versions and architecture; inspect source where feasible; avoid unnecessary compiled externals; prefer Pd Vanilla for the first prototype; use explicit namespaces where appropriate; keep dependencies documented.

### 11. Data poisoning and bad inputs

A beautiful patch cannot make bad source data good.

Possible problems include incorrect unit counts, stale statuses, duplicate projects, incorrect identifiers, missing projects, incompatible definitions, or manipulated inputs.

Protection: validate before visualization; retain provenance; represent conflicts instead of silently reconciling them; log transformations; make UNKNOWN visible.

### 12. The beautiful harmful machine problem

A system can be elegant, fast, mathematically consistent, and visually understandable and still be harmful.

The question is not merely:

**Does the patch work?**

It is also:

**What is the patch doing to whom, under whose authority, using whose data, according to whose rules, with what ability to challenge the result?**

## Human agency requirement

The interface should help people understand systems without silently becoming the authority that decides for them.

### EXPLAIN MODE
Shows what the documented system says.

### AUDIT MODE
Shows where records, definitions, timing, responsibility, or outcomes diverge.

### EXPERIMENT MODE
Allows hypothetical changes to model assumptions.

### DECISION MODE
**Not automatically authorized.**

If a future system is ever used for real decisions affecting people, that requires a separate governance, legal, accessibility, privacy, and accountability analysis.

## Do not optimize for efficiency alone

For housing, a dangerous objective function could be:

maximize units / minimize cost / minimize time

without constraints for affordability, accessibility, preservation, displacement, household stability, environmental impacts, legal rights, due process, or privacy.

The research model should therefore avoid a single universal housing-efficiency score.

## Warning labels for simulations

Every simulation screen should make clear:

**SIMULATION — NOT A PREDICTION**

**MODEL INPUTS — NOT OBSERVED FACTS**

**RESULTS DEPEND ON ASSUMPTIONS**

**SOURCE DATA AND PROVENANCE SHOULD BE AVAILABLE**

## Minimum abuse-resistance checklist

- What personal data does it contain?
- Can the same result be produced without personal data?
- Who can change the rules?
- Are rules visible?
- Are rule sources documented?
- Can a person challenge an incorrect input?
- Can a project be corrected?
- Are historical states preserved?
- Are unknowns visible?
- Are simulations clearly labeled?
- Are source records preserved?
- Are transformations logged?
- Are dependencies documented?
- Can the system be used to exclude someone?
- Can the system optimize a harmful objective?
- What happens if the data are wrong?
- What happens if the software is compromised?
- What happens if the institution using it changes its objective?

## Relationship to the project's grace principle

The project's broader research language includes forgiveness, restraint, and preservation of future choice.

In technical terms, those ideas can become design requirements:

**REVERSIBILITY** — A mistaken state can be corrected.

**EXPUNGEMENT / RETENTION CONTROL** — Information does not persist forever merely because storage is possible.

**RESTRAINT** — The system does not collect, infer, or automate more than necessary.

**CHALLENGE** — People can contest important records and decisions.

**FUTURE CHOICE** — A temporary administrative state does not automatically become a permanent identity.

These are proposed design principles, not claims about what Pd itself provides.

## Bottom line

Pure Data is a tool.

The housing transmission interface is a proposed research instrument.

Neither one determines whether a system is good or harmful.

The danger begins when visual dataflow becomes **unexamined authority**.

The project should therefore keep asking:

> **Who benefits? Who is exposed? Who can be harmed? Who can challenge it? What happens when the objective changes?**

alongside every technical question.