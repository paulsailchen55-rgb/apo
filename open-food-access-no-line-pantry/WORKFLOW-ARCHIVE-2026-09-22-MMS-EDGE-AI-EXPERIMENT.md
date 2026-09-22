# Workflow Archive — MMS / Edge-AI Experimental Gateway

**Date:** 2026-09-22  
**Evidence status:** PROPOSED / EXPERIMENTAL

## New understanding

The generalized resource-guide system should not assume that guides arrive only through web URLs or manual file uploads. A paper guide photographed on a phone could enter the system through MMS.

SMS and MMS therefore represent two related but different transport roles:

- **SMS:** text conversation and navigation.
- **MMS:** media/document intake and, where supported, media responses.

## Experimental architecture

**Community phone/gateway → local computer → edge AI/OCR → resource records → verification → messaging response**

A USB-C-connected phone is one possible prototype arrangement. This is an implementation hypothesis, not a guaranteed capability of all phones/carriers.

## Important limitation

A single gateway is a prototype, not a scalable public service.

The number of simultaneous conversations is constrained by the gateway, carrier, hardware, inference workload, message throughput, and software architecture. The project should therefore use a queue and explicit session state rather than assuming unlimited parallel conversations.

The correct next question is empirical:

> How many concurrent sessions can a specified low-cost gateway process while preserving acceptable response time and reliability?

## Security consequence

MMS attachments must be treated as untrusted input. The system should validate and isolate media processing, preserve provenance, avoid executing document content, minimize retention, and avoid requesting sensitive documents unnecessarily.

## Reusable architectural consequence

The **transport layer must remain separate from the resource-navigation engine**.

That allows the same core system to be connected later to:

- an experimental phone gateway;
- a dedicated cellular modem;
- a community-hosted messaging gateway;
- another standards-compliant messaging transport.

The resource database and conversational logic should not depend on one particular phone.

## Next waypoint

Create a minimal prototype that accepts one photographed guide, records its provenance, extracts candidate resource records, marks them NEEDS REVIEW, and returns a concise message.

Do not make claims about large-scale concurrency until measured.
