# Selective Librarian — Open Data and Human-Scale Information Access

Status: PROPOSED / RESEARCH DIRECTION

## Core idea

Government and other public institutions can publish very large amounts of information without expecting any one person to read everything.

A public record can be open and still be practically inaccessible if the volume, structure, terminology, or search burden exceeds what a person can reasonably process.

The proposed **Selective Librarian** is an information-access layer between an open public record and a human question.

It should not replace the underlying record.

It should help a person find the parts of the record that are most relevant to the question they are actually asking.

## The problem

Official records can be hundreds or thousands of pages long. Across agencies and jurisdictions, the total information volume can become much larger than any individual can realistically inspect.

AI can help process large document collections, but AI also has finite context, computation, retrieval, attention, and service limits.

Therefore the design problem is not simply:

> How do we summarize more information?

It is:

> How do we preserve the full information environment while helping a human selectively reach the evidence that matters to their question?

This is an information-retrieval and human-computer-interface problem as much as an AI problem.

Recent information-retrieval research also treats cognitive load, working-memory limits, interactive search, and user control as important design considerations. Retrieval systems can reduce extraneous load by fetching targeted material, while human-centered research warns that automated filtering can also reduce user control or hide relevant material if the system becomes a gatekeeper rather than an aid.

## The architecture

The proposed architecture is:

OPEN PUBLIC RECORD
→ INDEX / METADATA / IDENTIFIERS
→ SELECTIVE LIBRARIAN
→ HUMAN QUESTION / INTEREST
→ RELEVANT DOCUMENTS
→ RELEVANT SECTIONS
→ RELEVANT EVIDENCE
→ HUMAN INVESTIGATION

The library remains intact.

The librarian provides navigation.

The person remains the investigator.

## Not the same as synthesis

This distinction is important.

### Synthesis

Synthesis asks:

> What does this large body of material collectively say?

### Selective retrieval

Selective retrieval asks:

> Which existing records, documents, pages, tables, paragraphs, events, or data fields should I look at for this particular question?

### Selective highlighting

Selective highlighting asks:

> Within those records, which passages or relationships deserve my attention first, and why?

The Selective Librarian concept combines these functions carefully but does not collapse them into one opaque answer.

A system may provide a short explanation, but the underlying documents and evidence should remain reachable.

## Human-scale information standard

A future public-data standard could recognize two simultaneous audiences:

1. **Human readers**
2. **Machine readers**

The standard should not require government to reduce the original record merely because the record is large.

Instead, it should provide structure that allows machines to navigate the large record without destroying relationships that a human may later need.

Useful structural fields could include:

- document identifier
- agency
- jurisdiction
- subject
- date
- reporting period
- document type
- section / heading
- page or location
- project identifier
- dataset identifier
- related record identifiers
- source system
- publication status
- version
- update timestamp
- provenance
- accessibility information
- machine-readable representation where available

## The librarian should be able to say why

A selective system should not merely return:

> Here are five documents.

It should be able to explain:

- why each document was retrieved;
- which part of the user's question it appears to address;
- which section or record contains the relevant evidence;
- whether the evidence is direct, indirect, calculated, or interpretive;
- what important uncertainty remains;
- what related records were found;
- what the system did not retrieve or could not evaluate.

The person should be able to broaden or narrow the search.

## Zoom rather than flatten

This connects directly to the project's existing **zoom / fractal interface** idea.

A person could move through levels:

PUBLIC RECORD
→ DOMAIN
→ PROGRAM
→ PROJECT
→ EVENT
→ DOCUMENT
→ SECTION
→ EVIDENCE

The system should make it possible to zoom in without losing the path back out.

The small answer should therefore remain connected to the larger information field.

## Housing Transmission Audit application

The housing project provides a concrete test case.

The current housing transmission chain is:

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

A Selective Librarian could let a researcher ask:

> Where does this project's affordability status change?

The system could retrieve the relevant Housing Element record, project record, financing record, permit record, occupancy or affordability monitoring record, and related documents.

The system should not manufacture a new “housing truth” from those records.

It should expose the path between them.

## Connection to standardized machine-readable project data

This concept extends the project's existing standardized machine-readable housing project data work.

A standardized project record provides structure.

The Selective Librarian provides navigation.

The Pure Data interface provides an optional visual/experimental layer.

The relationship becomes:

GOVERNMENT STANDARD DATA
→ PERSISTENT IDENTIFIERS
→ DOCUMENT / RECORD INDEX
→ SELECTIVE LIBRARIAN
→ RELEVANT EVIDENCE
→ PURE DATA / GIS / DASHBOARD / HUMAN RESEARCH

The government does not need to use Pure Data.

The government does need data that other tools can understand if interoperability is the goal.

## Connection to the durable public-input archive

This also extends the project's official-synthesis-versus-durable-archive work.

The archive preserves the complete underlying public record.

The Selective Librarian helps a person navigate that archive.

Official synthesis remains a separate layer.

The architecture is therefore:

RAW PUBLIC RECORD
→ DURABLE ARCHIVE
→ INDEX / IDENTIFIERS
→ SELECTIVE LIBRARIAN
→ HUMAN QUESTION
→ RELEVANT RECORDS
→ OPTIONAL OFFICIAL OR RESEARCH SYNTHESIS

**Synthesis limits should not become archival limits.**

## Selective librarian versus selective gatekeeper

This is a central warning.

A system that decides what a person sees can become a gatekeeper even if it is described as a librarian.

The system therefore needs safeguards:

- underlying records remain accessible;
- retrieval criteria are inspectable;
- users can change search terms and scope;
- users can request broader results;
- users can inspect source documents;
- source provenance is preserved;
- uncertainty is visible;
- excluded or unavailable material can be disclosed where appropriate;
- personalization should not silently manipulate the user's conclusions;
- sensitive personal information should not be used merely because it is available;
- the user can reject the system's relevance interpretation.

The system should assist attention, not own attention.

## Personal relevance without personal manipulation

The user's stated question, project, or selected interests can help determine relevance.

That does not mean the system should infer hidden political, medical, psychological, religious, financial, or other sensitive traits and use them to shape what the person is allowed to see.

A safer design starts from explicit user-provided intent:

> “I am researching housing permitting.”

rather than silently deciding:

> “This is what this person probably needs to believe.”

The distinction is critical.

## Evidence discipline

The Selective Librarian should preserve the project's evidence tags:

- **KNOWN**
- **CALCULATED**
- **TESTED**
- **PROPOSED**
- **SPECULATIVE**
- **UNKNOWN**

Retrieval should not convert a proposed relationship into a known fact.

A highlighted passage is evidence to inspect, not automatically a conclusion.

## Cognitive-load principle

The objective is not to maximize the amount of information shown.

It is to maximize useful access to the underlying information while respecting human limits.

The machine can do the exhausting first-pass work:

- indexing;
- matching;
- locating;
- clustering;
- identifying repeated identifiers;
- finding related records;
- locating sections;
- comparing versions;
- surfacing candidate evidence.

The human can then spend more of their limited attention on:

- interpretation;
- verification;
- judgment;
- context;
- questions;
- disagreement;
- decisions.

This is an allocation of effort, not a replacement of human judgment.

## AI limits remain part of the architecture

The system must explicitly account for machine limitations:

- finite context windows;
- retrieval errors;
- incomplete indexing;
- token and compute limits;
- service limits;
- hallucination;
- ranking errors;
- ambiguous user questions;
- stale data;
- inaccessible documents;
- OCR errors;
- conflicting records;
- incorrect entity matching.

A machine-readable standard should therefore make provenance and traceability easier, not merely make documents easier for AI to consume.

## Failure modes to test

1. **Over-compression** — relationships disappear because the source is summarized too aggressively.
2. **Relevance tunnel** — the system repeatedly retrieves what it already thinks is relevant.
3. **False omission** — an important record is absent but the user assumes it was searched.
4. **Authority laundering** — an AI-selected passage appears more authoritative than the underlying source.
5. **Personalization drift** — user context changes retrieval in ways the user did not request.
6. **Search opacity** — the person cannot determine why something was selected.
7. **Archive blindness** — old or poorly indexed material becomes effectively invisible.
8. **Machine ceiling** — the system can only retrieve what its own index or model can understand.
9. **Context collapse** — a passage is technically relevant but loses the surrounding qualification.
10. **Human exhaustion** — the interface returns too much material and merely recreates the original problem.

## Minimum user interface

A first prototype does not need a sophisticated AI agent.

It could expose:

1. **What are you trying to understand?**
2. **What jurisdiction / project / subject?**
3. **What time period?**
4. **What source types should be included?**
5. **Show relevant records.**
6. **Show why each was selected.**
7. **Open the original.**
8. **Broaden search.**
9. **Narrow search.**
10. **Show related records.**
11. **Show uncertainty / missing records.**
12. **Save the research path.**

The saved research path is important because another person should be able to reproduce how the evidence was found.

## Relationship to the APO archive

This concept belongs across several existing APO projects rather than being treated as an isolated application.

Primary home:

- santa-cruz-housing-subsidy-stack/

Direct conceptual relatives:

- information-archaeology-and-information-half-life/
- civic-flow-chart/
- civic-two-minute-ideas/
- unified-civic-input-platform/
- wayfinder-community-access/
- relational-highlighter-limitless-v0-1/
- ai-mediated-influence-threat-model/
- the-peoples-relay-archive/

The shared theme is not “AI summarizes everything.”

It is:

> **Preserve the information field, then build accountable ways for humans to navigate it.**

## Research questions

- What existing government standards already provide persistent identifiers?
- Can a project be followed from planning through occupancy using stable identifiers?
- Which public records are machine-readable today?
- Which are only available as PDFs, scans, webpages, or images?
- How should document sections and page locations be represented?
- How can a retrieval system prove what it searched?
- How should relevance be evaluated without letting the AI define its own truth set?
- How can users inspect what was excluded?
- How should old or poorly indexed records be surfaced?
- What is the smallest metadata standard that enables useful navigation?
- How can a person move from a machine-selected passage back to the complete original?
- How can multiple tools use the same record structure?
- What safeguards prevent a Selective Librarian from becoming a Selective Gatekeeper?

## Design principle

> **Do not make the public record smaller just because humans and machines have limited attention. Make the public record more navigable.**

And:

> **The librarian should help a person find the book. The librarian should not become the book.**

## External research note

The concept is consistent with established information-retrieval work on interactive search, cognitive load, human-machine division of labor, and library/reference assistance. Current research also identifies risks when AI systems automatically filter or personalize information access, including reduced user control and biased or incomplete retrieval.

Those sources support the research direction; they do not establish that this proposed architecture has been validated.

## Status

**PROPOSED / RESEARCH DIRECTION**

No claim is made here that a complete Selective Librarian system already exists or that the proposed safeguards are sufficient. The next step is to test the architecture against real public records while preserving the original sources and the user's ability to inspect them.
