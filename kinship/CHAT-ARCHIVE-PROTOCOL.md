# KINSHIP Chat Archive Protocol

KINSHIP is developed through conversation as well as formal engineering work. Conversation contains design provenance that can be lost if only final conclusions are retained.

## Working rule

**Every substantive KINSHIP conversation receives an archival pass.**

The user may explicitly request preservation at any point with a simple command such as:

**“Archive this.”**

or:

**“Push this to the KINSHIP archive.”**

The assistant should then preserve the valuable material available in the current working context rather than relying on later recall.

At the end of a substantive conversation, a broader archival pass should also be performed when requested or when the user indicates the conversation should be archived.

## Archival granularity

The preferred preservation granularity is finer than a single end-of-project summary.

If an individual response, exchange, or section contains important technical, conceptual, or historical material, it may be archived before the conversation moves much farther away from it.

The goal is not necessarily verbatim transcription. The goal is preservation of **critical detailed points** sufficient for later functional reuse.

A useful archive should preserve, where applicable:

- the problem being addressed;
- new concepts;
- design decisions;
- design principles;
- important original wording;
- research questions;
- open questions;
- discovered problems or failure modes;
- proposed experiments;
- calculations or quantitative reasoning;
- evidence or tested results;
- terminology;
- connections to earlier work;
- material suitable for canonical documentation;
- provenance and intellectual history.

Over-simplification is a failure mode. A short summary that preserves only the general topic is not an adequate substitute when technical or conceptual detail may be needed later.

## Working category checklist

Until a dedicated selection interface exists, use this as the manual equivalent of a checkbox-based archival selector:

- [ ] Project definition
- [ ] New technical concept
- [ ] Design decision
- [ ] Design principle
- [ ] Important original wording
- [ ] Research question
- [ ] Open question
- [ ] Problem or failure mode discovered
- [ ] Proposed experiment
- [ ] Calculated/quantitative material
- [ ] Evidence or tested result
- [ ] Terminology/glossary material
- [ ] Connection to earlier project work
- [ ] Material for canonical documentation
- [ ] Conversation/provenance history
- [ ] Temporary brainstorming
- [ ] Personal/non-project discussion

The user may effectively deselect categories by telling the assistant what not to preserve.

## Project classification

A conversation does not need to be declared a project at the beginning.

A useful progression is:

**OPEN CONVERSATION → PROJECT IDENTIFIED → PROJECT DESTINATION ESTABLISHED → SUBSEQUENT CONVERSATIONS ARCHIVED TO THAT PROJECT**

Once KINSHIP is established as the project destination, subsequent KINSHIP conversations should be treated as part of that project unless the user explicitly separates them.

Not every archived conversation becomes canonical project documentation.

## Two-layer record

KINSHIP should maintain both:

- **conversation/provenance records**, preserving how ideas emerged;
- **canonical engineering documents**, progressively refining the ideas into requirements, models, tests, and evidence.

The canonical document may become cleaner than the conversation. The provenance record should not be rewritten merely to make history cleaner.

A third layer may be used when appropriate:

- **evidence/test records**, preserving calculations, experimental results, measurements, simulations, and other technical evidence.

## Promotion rule

After archiving a conversation, identify material that should be promoted into canonical KINSHIP documentation.

Promotion should be conservative and traceable. Do not turn every exploratory statement into an engineering requirement.

Use the project's evidence discipline:

**KNOWN** — supported by established evidence.

**CALCULATED** — derived from an explicit model.

**TESTED** — demonstrated experimentally.

**PROPOSED** — design hypothesis.

**SPECULATIVE** — interesting but presently unvalidated.

**UNKNOWN** — requires investigation.

## Provenance rule

Never silently overwrite earlier provenance.

When a concept evolves, preserve the earlier conversation record and update the canonical document separately. Where practical, identify the conversation/archive record that originated or materially changed the idea.

## Repository rule

Use GitHub as the durable external project record.

For KINSHIP, the repository location is the established KINSHIP folder inside the APO archive repository.

Never modify APO root documentation unless the user explicitly requests it.

## Important limitation

The assistant cannot assume that an old conversation will remain available indefinitely. If a conversation contains important KINSHIP material, archive it while it is available rather than relying on future recall.

## Workflow principle

> **The conversation is the workshop. The repository is the durable project record. Valuable work should be moved from the workshop to the record before distance from the original conversation can erase the detail.**
