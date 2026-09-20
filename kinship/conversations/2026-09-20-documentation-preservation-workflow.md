# 2026-09-20 — Documentation Preservation Workflow

## Context

During review of the KINSHIP archive, the project was found to contain an earlier five-file conceptual archive while a later conversation had established a much more comprehensive Phase 25–27 repository architecture.

The Phase 25–27 discussion was preserved verbatim in:

`00-phase-25-27-repository-architecture-verbatim.md`

The purpose of this conversation was to establish a better workflow so that important design material does not become lost as the conversation history grows.

## Working decision

KINSHIP development will use two linked records:

1. **Canonical documents** — progressively refined engineering, research, requirements, safety, testing, and deployment documents.
2. **Conversation/archive records** — dated records preserving significant design provenance and, when useful, original wording.

At the end of a significant KINSHIP conversation, the user can explicitly request that the conversation be archived. The assistant should identify reusable material, preserve important provenance, update the appropriate canonical document(s), and update the changelog when appropriate.

## Repository scaffold

The expanded Phase 25–27 document structure is being established now as a scaffold. Empty or preliminary documents are intentionally marked as such rather than being filled with invented engineering certainty.

## Evidence discipline

The project continues to use:

- KNOWN
- CALCULATED
- TESTED
- PROPOSED
- SPECULATIVE
- UNKNOWN

## Important principle

Do not rely on future conversational recall as the sole archive of important KINSHIP work. GitHub should function as the durable external project record, while conversations remain an active development medium.
