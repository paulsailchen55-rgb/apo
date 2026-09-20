# KINSHIP Conversation Archive — Documentation Preservation Workflow

**Date:** 2026-09-20  
**Subject:** Conversation-level preservation, archival granularity, and repository workflow  
**Status:** Proposed workflow adopted for testing

## Why this conversation matters

This conversation identified a failure mode in the earlier KINSHIP documentation workflow: waiting until the end of a substantial conversation, or relying on a later summary, can cause useful detail to disappear. The user has observed this across roughly 50 conversations and noted that older conversations may no longer retain enough accessible context after many later chats. Some conversations have also been deleted after being considered clutter.

The practical consequence is that a final, overly compressed project summary is not sufficient as the project's durable record. The archive needs enough technical, conceptual, and historical detail that another person could later use the material rather than merely understand that a discussion occurred.

## User's requested direction

The user described an ideal future interface in which each conversation response or section could expose selectable archival categories, with checkboxes that could be selected automatically and then deselected for material the user does not want preserved. They also described a possible end-of-conversation control that would offer repository destinations and ask whether the conversation is a project, an open conversation, or another category.

The exact interface is not presently the workflow being implemented here. The important design requirement is the behavior:

- preserve valuable material at a much finer granularity than occasional end-of-project summaries;
- make selective exclusion possible;
- distinguish projects from open conversations;
- maintain a durable repository destination once a project has been established;
- retain enough detail for later functional reuse;
- avoid requiring the user to manually copy and paste every conversation.

## Important refinement to the previous archive protocol

The earlier protocol said:

> "At the end of a significant KINSHIP conversation..."

This conversation refined that principle.

### New working rule

**Every substantive KINSHIP conversation should receive an archival pass.**

This does **not** mean every conversation becomes a canonical engineering document.

Instead, there are three progressively stronger preservation levels:

1. **Conversation archive** — preserve the useful intellectual and technical content of the conversation with sufficient detail for future reuse.
2. **Canonical project documentation** — promote conclusions, requirements, models, research findings, design principles, or other durable material into the appropriate KINSHIP document.
3. **Evidence/test record** — when an idea becomes calculated, tested, or otherwise evidence-backed, preserve the corresponding technical record.

This is intentionally different from treating every chat as a project.

## Granularity lesson

The user specifically rejected the idea that a useful archive should be reduced to a short summary merely because it is not intended to be verbatim.

The archive should preserve **critical detailed points**.

A good archive therefore should answer questions such as:

- What was the user actually trying to solve?
- What new idea appeared?
- What distinction was made?
- What design principle was established?
- What alternatives were considered?
- What was rejected or excluded?
- What uncertainty remained?
- What technical vocabulary or terminology was introduced?
- What connections were made to existing KINSHIP work?
- What should eventually be promoted into canonical documentation?
- What wording is important enough to preserve because it captures the origin of an idea?

A summary that retains only the general theme is inadequate when the lost details could later be needed to reconstruct or develop the work.

## Per-response preservation as an experimental workflow

The user proposed going even finer than the end-of-conversation archive: when an individual assistant response contains valuable material, it should be possible to preserve that material before the conversation moves many turns farther away from it.

This should be treated as a workflow experiment.

The practical command can remain simple. For example:

> **"Archive this."**

or:

> **"Push this to the KINSHIP archive."**

When such a command is given, the assistant should preserve the relevant material from the current working context rather than waiting for the conversation to end.

The important principle is:

**Do not allow valuable material to become dependent on later conversational recall.**

## Proposed archival categories

The user described a checkbox-style selection model. Until such an interface exists, the following categories can serve as the manual equivalent:

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
- [ ] Connection to earlier KINSHIP work
- [ ] Material for canonical documentation
- [ ] Conversation/provenance history
- [ ] Temporary brainstorming
- [ ] Personal/non-project discussion

These categories are a **working prototype**, not a final UI specification. They should be revised after practical use.

## Project classification

A conversation does not need to be declared a project at the beginning.

A useful workflow is:

**OPEN CONVERSATION → PROJECT IDENTIFIED → PROJECT DESTINATION ESTABLISHED → SUBSEQUENT CONVERSATIONS ARCHIVED TO THAT PROJECT**

Once KINSHIP is established as the project destination, subsequent KINSHIP conversations should be treated as part of the same project unless the user explicitly separates them.

## Relationship to canonical documentation

The repository should contain both:

### Historical/provenance records

These preserve how ideas developed and should not be rewritten simply to make the history cleaner.

### Canonical engineering documents

These progressively refine ideas into requirements, models, calculations, tests, evidence, and implementation guidance.

The two records serve different purposes. A canonical document may become concise and formal. The conversation archive should retain the detail necessary to understand where the formal material came from.

## Why this is especially important for KINSHIP

KINSHIP contains many ideas that begin as exploratory conversation and may later become engineering questions. Examples include adaptive operating modes, articulated environmental manipulators, controlled anchoring and release, transforming protective enclosure systems, aquatic mobility, repair architecture, and material research.

If the intermediate reasoning is discarded, later engineering work may retain the conclusion while losing the reason the question was asked, the constraints that shaped it, or alternatives that were already considered.

Therefore:

**Conversation history is part of the project's research provenance.**

## Operational conclusion

For future KINSHIP work, the preferred workflow is:

1. Explore freely in conversation.
2. When a response or group of responses contains durable value, archive it rather than relying on later recall.
3. At the end of a substantive conversation, perform a broader archival pass.
4. Preserve detailed material in the conversation archive.
5. Promote mature material into canonical documents.
6. Keep hypotheses, proposals, calculations, tests, and known facts clearly distinguished.
7. Preserve provenance when canonical documents evolve.
8. Use GitHub as the durable external project record.
9. Leave the APO root documentation untouched unless explicitly requested.

## Key principle

> **The conversation is the workshop. The repository is the durable project record. Valuable work should be moved from the workshop to the record before distance from the original conversation can erase the detail.**

## Scope note

This record documents the KINSHIP workflow discussion. It does not establish that the proposed checkbox UI, automatic per-response repository control, or automatic project classification currently exists as a ChatGPT feature. Those are workflow/interface requirements identified by the user and may be useful as a future product or tooling concept.
