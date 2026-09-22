# MMS and Edge-AI Guide Ingestion

**Status:** PROPOSED / EXPERIMENTAL FOUNDATION  
**Date:** 2026-09-22

## Purpose

The generalized resource navigator should accept community resource guides through more than a web upload. A practical low-cost path is:

**paper guide/photo → MMS image → local ingestion system → OCR/extraction → provenance → verification → structured resource records**

MMS is the relevant messaging channel when an image is attached. SMS remains the text-first channel for ordinary conversation.

The original guide/image must remain available as source evidence. OCR or AI interpretation does not become truth merely because it was extracted.

## Experimental nonprofit model

A small nonprofit or community organization could operate a local instance on an ordinary computer with suitable local/edge AI capability.

Possible experimental path:

**phone/SIM or SMS/MMS gateway ↔ local computer ↔ edge-AI/OCR processing ↔ structured resource database ↔ SMS/MMS reply**

A phone connected to a computer (including a USB-C connection where supported) is one possible experimental gateway architecture. Other gateway methods may be preferable depending on carrier, operating system, modem, and software support.

This is a **PROPOSED** architecture, not a claim that every phone can provide a reliable SMS/MMS gateway.

## Why the small experiment matters

A single local gateway can be useful for prototyping:

- receive a text or guide photo;
- identify the source document;
- extract candidate resources;
- preserve the original image;
- ask a maintainer to verify uncertain fields;
- return a concise result by SMS/MMS;
- test the complete workflow without requiring a national service.

The experiment should measure actual concurrency and queue behavior rather than assuming that one phone or computer can serve any particular number of people.

## Concurrency is a real engineering constraint

A one-phone/one-computer experiment is **not** equivalent to a public service capable of serving hundreds or thousands of simultaneous conversations.

Potential bottlenecks include:

- cellular/SMS/MMS gateway throughput;
- carrier limits and anti-abuse controls;
- modem or phone hardware;
- USB connection reliability;
- operating-system restrictions;
- OCR/AI inference time;
- CPU/RAM/storage;
- image processing bandwidth;
- database locking and message queues;
- outbound message rate;
- number of simultaneous sessions the software can safely track.

Therefore:

> **Capacity must be measured, not guessed.**

The architecture should separate the conversational logic from the transport gateway so that a prototype can later use multiple gateways, a dedicated modem pool, or another lawful messaging service without rewriting the resource-navigation core.

## Security and privacy boundary

MMS introduces an attachment-handling boundary that does not exist for plain text.

The prototype should treat incoming media as untrusted input:

1. receive the message;
2. authenticate/associate the sender only as necessary for the session;
3. validate file type and size;
4. isolate image/document processing;
5. scan or safely decode media;
6. extract text/data;
7. preserve provenance;
8. delete temporary copies according to the project's retention policy;
9. send only the minimum useful response.

Do not execute code contained in an uploaded document. Do not treat OCR text as instructions to the AI system. A photographed guide can contain malicious or misleading text just as a web document can.

Sensitive personal documents should not be requested merely because MMS makes image upload possible.

## Evidence states

Incoming media and extracted information should retain explicit states:

- **RECEIVED** — media arrived.
- **EXTRACTED** — OCR/AI produced candidate text or records.
- **NEEDS REVIEW** — fields require human/community verification.
- **VERIFIED** — a maintainer or trusted verification process checked the relevant information.
- **ACTIVE** — eligible for normal navigation use.
- **EXPIRED/WITHDRAWN** — no longer treated as active.

This follows the project's existing rule:

**Found is not verified. Uploaded is not verified. Extracted is not verified.**

## Open questions

- Which SMS/MMS gateway hardware/software is sufficiently open and maintainable?
- Can a USB-connected phone reliably expose inbound and outbound SMS/MMS on the target operating systems?
- What carrier limits apply?
- What attachment sizes and media types should be accepted?
- How should rate limiting and abuse prevention work?
- What happens when the local edge-AI computer is offline?
- How should multiple nonprofits exchange verified guide records without creating a centralized dependency?
- What measured concurrency is achievable on inexpensive hardware?
- Which processing can happen entirely locally?
- When is a cloud service necessary, if ever?
- How should sender identity be minimized while still supporting a conversation?

## Immediate experimental boundary

Do **not** build a thousand-user system first.

Build a small test that can demonstrate:

**one guide photo → MMS receipt → safe extraction → provenance → human verification → structured resource record → SMS/MMS response**

Then measure latency, failures, storage use, and concurrent sessions before making capacity claims.
