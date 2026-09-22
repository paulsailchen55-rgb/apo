# Workflow Archive — AI Coding Prompt Modularization and Interface Model

**Date:** 2026-09-22  
**Project:** Open Community Resource Access & No-Line Navigator  
**Folder:** `open-food-access-no-line-pantry/`  
**Evidence status:** Conversation understanding = **KNOWN**; prompt changes = **PROPOSED / BUILD INSTRUCTION**; implementation architecture = **PROPOSED**

## Purpose

This archive preserves the understanding added to `AI-CODING-BUILD-PROMPT.md` after reviewing how a future coding AI should work with this project.

The project owner expects the build prompt to evolve through multiple versions. The prompt is therefore a living implementation instruction, while workflow archives preserve the reasoning and transition that produced each meaningful version.

## What was settled

### 1. The first prompt is intentionally a first version

The prompt is considered sufficient for an initial build-instruction version. It is expected to evolve through future iterations as actual coding agents, tools, tests, and implementation experience reveal what needs clarification.

The objective is not to predict every future AI workflow.

### 2. Different coding AIs may require different execution workflows

Different AI coding environments may have different:

- tool capabilities;
- agent instructions;
- work-order conventions;
- context limits;
- repository access;
- file-editing mechanisms;
- testing workflows;
- official guidance.

The prompt therefore distinguishes between:

**project principles and constraints** versus **the execution procedure used by a particular AI environment**.

A future coding AI should adapt its execution procedure to its environment, including reading official platform-specific coding guidance when practical, without changing the project's underlying principles merely to fit that platform.

## 3. Repository documents have different roles

A future AI should not flatten every Markdown file into one specification.

The intended distinction is:

- current project documents = current architecture/design/roadmap/safety/open questions;
- `AI-CODING-BUILD-PROMPT.md` = what a coding AI is currently being asked to build and how it should operate;
- `WORKFLOW-ARCHIVE-*.md` = historical reasoning and project evolution;
- practice/test artifacts = behavior demonstrations and tests;
- experimental documents = possible technical approaches that remain uncertain.

This distinction was added directly to the build prompt.

## 4. Three interfaces, one system

The three interfaces remain:

1. Photograph/upload a guide.
2. Text-first navigation / backup wayfinding.
3. Continue the journey after arrival.

They are not three separate applications.

They are replaceable interfaces/adapters to the same underlying resource-access system.

## 5. The Lego / Smalltalk-like modularity insight

The project owner described the interfaces as Lego-like: a module should be capable of being plugged in, removed, or replaced without destroying the useful underlying system.

The important test is therefore not merely:

> “Is this code in a separate folder?”

The stronger test is:

> “Can this interface be removed or substituted while the underlying resource-access system remains usable?”

This leads to a message-oriented modular design principle:

- interfaces translate human input into operations on the underlying system;
- the core exposes explicit contracts;
- the interface should not need to know the core's internal implementation;
- core resource/access logic should not be duplicated in each interface.

The prompt now identifies possible contracts including source ingestion, resource retrieval, provenance, time/status/eligibility/access evaluation, journey state, next-action requests, point-of-service obstacles, and alternatives.

## 6. First build: modular vertical slice

The settled direction is neither:

- three separate applications built independently to completion;

nor:

- one giant application with all three interfaces tightly coupled.

Instead:

**Build the smallest end-to-end vertical slice that exercises all three interfaces while preserving replaceable boundaries.**

The intentionally tiny demonstration can be:

**guide image → extracted resource → provenance/review state → text request → useful action → simulated arrival → point-of-service obstacle → context-aware next action**

This tests the architectural relationship while avoiding premature production infrastructure.

## 7. Build order now reflects modular adapters

The preferred work order is:

1. generic source-guide/document model;
2. generic resource-record schema;
3. provenance/evidence lifecycle;
4. one historical guide fixture;
5. one food and one non-food resource fixture;
6. time/status/eligibility/access evaluation;
7. small replaceable Interface A adapter;
8. small replaceable Interface B adapter;
9. small replaceable Interface C adapter;
10. connect A+B+C through the shared core in one end-to-end demonstration;
11. queue/concurrency measurement;
12. additional transports;
13. broader guide discovery.

This is a work order, not a statement that the interfaces are separate systems.

## 8. What remains experimental

The following remain experimental or unknown and must not be represented as solved merely because they appear in the build prompt:

- actual SMS/MMS gateway choices;
- USB-C phone gateway behavior;
- carrier capabilities and limits;
- local/edge AI/OCR performance;
- arbitrary guide OCR accuracy;
- public-service concurrency;
- production deployment;
- broad automated guide discovery.

The build prompt explicitly requires honest reporting of what is implemented, simulated, externally dependent, and unknown.

## 9. Non-destructive preservation

This transition does not replace or delete earlier archives.

The current build prompt is a living artifact.

Historical workflow archives remain historical artifacts.

A future revision of the prompt should not rewrite an older archive as though the later understanding had always been present.

## Evidence classification

### KNOWN
- The project owner explicitly wants the prompt to evolve through multiple versions.
- Different AI environments may require different execution procedures.
- The three interfaces are intended as modular interfaces to one underlying system.
- The Lego analogy expresses replaceability rather than merely separate folders.
- A small end-to-end demonstration is desired without coupling the interfaces into one monolith.

### PROPOSED
- Stable contracts between interfaces and the underlying resource-access engine.
- Replaceable interface adapters.
- The modular vertical-slice implementation order.

### UNKNOWN
- Which future coding AI will be used.
- Which platform-specific instructions it will provide.
- Which technical interface/contract mechanism will prove most useful in implementation.
- Whether every proposed transport can be substituted without additional adaptation.

## Transition

The build prompt was updated to incorporate this understanding.

The next meaningful step is implementation/testing of the modular vertical slice, followed by revision of the prompt based on actual evidence.

> **One underlying system, multiple replaceable interfaces.**

> **Build the smallest modular vertical slice before expanding the system.**

> **The project defines the principles; the coding environment determines the practical execution procedure.**
