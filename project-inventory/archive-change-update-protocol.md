# Archive Change-Update Protocol

**Purpose:** Keep `apo` useful as an archive and chat-loader without turning it into the project itself.

## Principle

**Preserve the possibility before deciding what it is.**

A conversation can contain projects, potential projects, research questions, frameworks, experiments, supporting ideas, writing concepts, and personal or philosophical exploration. The archive should preserve those distinctions.

## Archive pass

When a substantial conversation is ready to archive:

1. Examine the entire available conversation context.
2. Inventory distinct bodies of work before deciding where they belong.
3. Compare each item with existing `apo` folders and files.
4. Leave adequately represented material alone.
5. Add or update only where the conversation provides genuinely new, relevant material.
6. Preserve provenance and uncertainty.
7. Keep unrelated projects separate even when they share vocabulary or themes.
8. Record the archive pass and substantive changes.
9. Commit directly to `main` unless a different branch is requested.

## Change record

For a substantive update, preserve the date, body of work affected, what was already present, what was added or changed, why the change was made, unresolved questions, boundaries against neighboring projects, and relationship to any active implementation repository.

## Information status

Use explicit distinctions such as user observation, user proposal, interpretation, hypothesis, experiment, documented fact, external evidence, disputed claim, assistant-generated organization, and unresolved.

Do not upgrade one category into another merely because it appears repeatedly in conversation.

## Update versus overwrite

An archive update should preserve prior material. Prefer additive files or carefully scoped additions to existing files. Do not rewrite an older record merely to make it look current unless the record is explicitly intended to be a living reference file.

## Relationship to active projects

`apo` is a reference/archive/chat-loader repository. An active project may have its own implementation repository. The archive can contain conceptual history and reusable context without becoming the authoritative implementation.

## Root README rule

This protocol does not authorize modification of the root `README.md`. Root README changes require explicit user instruction.

## Minimality

The archive should be comprehensive enough to prevent loss of useful context, but should not create unnecessary duplicate copies of every project artifact.
