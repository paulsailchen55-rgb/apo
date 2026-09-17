# Functional Phone — Minimal Dependencies

## Status

Archive/reference package created 2026-09-17 from the phone-setup work in conversation.

This folder is a self-contained record of a practical experiment: making an older Android phone **boring, functional, and less exhausting**, with fewer app-level dependencies on Google and fewer cloud/sync requirements.

This is not presented as a finished de-Googling project, a security proof, or a new operating system. It is a reference package for a deliberately modest phone configuration.

## Core principle

> Keep the phone useful. Remove dependencies that are unnecessary. Change one thing at a time. Do not turn the phone into a maintenance hobby.

The desired endpoint is a phone that can handle calls and SMS, fast voice dictation and ordinary typing, web access, ChatGPT for research/writing/document work, local photos/files/documents, banking, and occasional Office-compatible document editing without requiring cloud photo sync, OneDrive, Google Drive, or a large collection of accounts and background services.

## Current experiment

The phone is an older Motorola Moto G Pure (2022). The phone is being treated as a temporary laboratory rather than something that must be made perfect.

Apps/configuration tested or selected during this work:

- **FUTO Keyboard** — chosen because integrated voice input is important and the project offers offline voice input.
- **Fossify Launcher** — tested as a simpler home screen.
- **Fossify Gallery** — selected for local photo/video management.
- **Fossify Messages** — selected for local SMS/MMS handling.
- **Firefox** — preferred non-Google browser.
- **ChatGPT** — retained as the user's AI/work assistant.
- **Banking app** — retained because banking is a required function.

Not installed yet / intentionally deferred:

- KeePassDX;
- Collabora Office;
- additional Fossify apps;
- alternative operating system;
- extensive de-bloating or package removal;
- cloud synchronization services.

## What "minimal" means here

Minimal does **not** mean removing every Google or Android system component. Android system infrastructure may remain underneath the apps the user actually uses.

The practical target is to reduce **user-facing dependency** and unnecessary cloud integration, while leaving core Android plumbing alone unless there is a concrete reason to investigate it.

## Current direction

Use the phone for a while before adding more software. If a missing capability becomes a real problem, solve that single problem rather than installing a whole suite of tools in advance.

See:

- `conversation-notes.md` — preserved context and reasoning from the setup conversation.
- `setup-plan.md` — current minimal configuration and deferred changes.
- `research-notes.md` — factual research and uncertainty notes supporting the choices.
