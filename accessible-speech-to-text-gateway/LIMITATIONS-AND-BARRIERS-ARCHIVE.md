# Limitations and Barriers Archive

## Purpose

This file preserves constraints discovered while investigating an accessible speech-to-text and AI gateway for people using inexpensive hardware and free or already-paid AI services.

The purpose is to prevent a failed experiment from being remembered only as “it didn't work.” Each constraint remains attached to the possibility it affected.

## 1. Dedicated / Wiped-Phone Concept

One possibility discussed was taking an inexpensive Android phone, wiping it down, and making it effectively a single-purpose device for recording speech, transferring or processing the recording, producing text, and handing that text to an AI.

Limitation discovered: wiping or simplifying the phone does not remove limitations imposed by the services used afterward. If a free AI tier permits only a limited number of file uploads, a workflow that produces many separate recording files can hit the service limit even though the phone can record them and transcription is technically possible.

Therefore, “one device” does not automatically mean “one unrestricted workflow.”

Evidence status: TESTED / OBSERVED; exact service limits are provider- and date-dependent and should be rechecked before implementation.

## 2. Free-Tier File-Count Limits

Free AI services can impose restrictions on the number of uploads. This matters because the desired walking workflow may deliberately create multiple files: stopping and starting after thoughts, splitting long recordings, or retrying failed chunks.

If the AI service accepts only a small number of files in its free tier, the workflow can fail at the ingestion layer before model capability becomes the issue.

Engineering consequence: the gateway should not assume that recording files can simply be sent directly to a free AI service. A separate transcription layer may need to turn many audio files into one or more ordinary text files first.

## 3. Free-Tier Quotas Are a Separate Layer

Free AI services may have restrictions involving uploads, file size, messages, context, daily or monthly usage, supported file types, processing availability, and rate limits. These restrictions can change independently of the underlying model.

Therefore, “the AI can understand this” and “the free consumer interface can accept this workflow” are different questions.

## 4. Long-Recording / Large-File Problem

One large file can avoid a file-count limit, but large files can encounter size, processing-time, memory, timeout, upload, or service restrictions. Many small files are easier to retry but can encounter file-count limits.

A gateway could accept the original long recording, split it internally, transcribe the pieces, recombine the transcript, and return one user-owned TXT/Markdown file. This moves segmentation away from the AI consumer interface.

## 5. Moto G Power 2024 Local-Processing Constraint

The Moto G Power 2024 was tested as the inexpensive target device. Small local AI models could run, but the tested applications did not provide useful access to the phone's GPU for the desired workload. Processing therefore fell back toward CPU-based computation, which was insufficient for the desired practical speech/AI workflow.

Consequence: the project cannot simply assume that a cheap Android phone can provide fast local Whisper/AI processing.

Evidence status: TESTED.

## 6. Chromebook Local Whisper Constraint

A Pentium Chromebook was tested with Whisper. A four-hour recording took more than 24 hours in the tested configuration.

Consequence: the Chromebook can still serve as a file-management device, browser interface, upload/download terminal, or control surface for remote compute, but the tested configuration is not suitable for rapid local transcription of long recordings.

Evidence status: TESTED.

## 7. Google Colab Demonstrated the Remote-Compute Path

Google Colab demonstrated that remote compute can process the workload much faster than the Chromebook.

Limitation: the notebook/upload workflow is cumbersome for everyday use and requires the user to understand too much infrastructure. Colab is evidence for the architecture, not necessarily the final user interface.

## 8. Philips VoiceTracer: Capture Hardware Does Not Solve the Compute Layer

The Philips VoiceTracer DVT1170 can solve part of the problem: speech to audio file. It does not itself solve audio file to fast transcript.

The recorder experiment reinforced the separation between capture, storage, transcription, and AI interpretation.

## 9. Recorder Storage / Battery Constraints

The DVT1170's published maximum recording/storage figures did not match the user's practical experience. Observed issues included internal storage appearing to fill after roughly 14 hours, earlier microSD experience lasting only several hours, and NiMH AAA batteries not lasting all day as hoped.

Consequence: capture devices must be evaluated under the actual intended recording mode, battery type, storage configuration, and workflow rather than headline specifications alone.

Evidence status: TESTED / OBSERVED.

## 10. BOYA Notra Subscription Constraint

BOYA Notra demonstrated a modern hardware/software approach closer to the desired workflow, but transcription minutes are tied to service tiers.

Previously investigated figures were approximately 320 minutes/month on the free tier, with a promotional increase to 600 minutes/month under specified conditions. Paid tiers provide more capacity.

Expected use discussed: approximately 7 hours/month = 420 minutes; approximately 14–16 hours/month = 840–960 minutes; an unusually large 24-hour recording = 1,440 minutes.

Consequence: a device can be technically capable while still failing the accessibility requirement if normal use requires another recurring subscription.

Evidence status: TESTED / RESEARCHED; pricing and allowances are time-sensitive.

## 11. Subscription Fragmentation

The investigation repeatedly encountered a layered system: capture device, operating system, speech recognition, transcription, storage, AI model, AI interface, and export.

Each layer may have different hardware requirements, pricing, quotas, file restrictions, privacy policies, APIs, subscriptions, and interoperability.

A user can therefore have access to one layer without having practical access to the complete workflow.

## 12. AI Subscription Does Not Equal Speech-to-Text Gateway

An existing AI subscription does not necessarily provide an unrestricted, convenient speech-to-text pipeline for long recordings.

The desired workflow is: “I talk. My words become a text file. Then I give that text to whatever AI I choose.”

The investigation found that consumer products can divide that workflow into separate capabilities.

Consequence: transcription should be treated as an independent service layer rather than assuming the final AI provider will always be the recorder, transcriber, storage system, and analyst.

## 13. Privacy vs. Free Remote Compute

Free remote computation is attractive because it solves the hardware problem, but sending personal recordings to remote infrastructure creates questions about retention, provider access, account requirements, upload security, temporary files, logging, deletion guarantees, and control of original audio.

Consequence: “free” and “private” cannot be treated as automatically equivalent.

## 14. Manual Cloud Workflow Is an Accessibility Barrier

A workflow can be technically free and still be practically inaccessible if it requires too many manual steps.

The Colab experiment illustrated this: record, find the file, open a notebook, upload, select a runtime, start processing, wait, locate the transcript, download it, open another AI, and upload the transcript.

The desired system compresses this toward: RECORD -> TRANSCRIBE -> GET TEXT, while preserving user control over where the text goes.

## 15. The Core Architectural Limitation

The limiting component can move between hardware, GPU access, CPU speed, storage, battery, operating system, browser, upload limits, file-count limits, file-size limits, transcription compute, AI quotas, subscriptions, network access, privacy requirements, and user-interface complexity.

Therefore the architecture should avoid making any one component responsible for the entire chain.

## 16. Design Principle Derived From the Limitations

CAPTURE DEVICE -> SIMPLE FRONT END -> AVAILABLE TRANSCRIPTION COMPUTE -> USER-OWNED TEXT -> USER-CHOSEN AI

rather than

ONE DEVICE -> ONE COMPANY -> ONE SUBSCRIPTION -> EVERYTHING

## 17. Evidence Categories

- KNOWN — documented limitation from a reliable source.
- CALCULATED — derived from measured quantities or published limits.
- TESTED — personally tested in the user's actual workflow.
- PROPOSED — possible solution not yet demonstrated.
- SPECULATIVE — hypothesis requiring investigation.
- UNKNOWN — information not yet established.

## 18. Barrier vs. Intent

The investigation establishes practical barriers and fragmentation. It does not by itself establish that these barriers were intentionally designed to exclude low-income users.

Research question: Does the current deployment architecture of consumer AI create systematic access barriers for people who lack high-performance hardware, reliable broadband, paid subscriptions, or the ability to maintain multiple proprietary services?

A related question is which barriers are intrinsic technical requirements and which result from packaging, pricing, service separation, proprietary interfaces, quotas, or lack of interoperability.

## 19. Central Observation

The project is not merely trying to make speech recognition work. It is investigating whether a person with inexpensive hardware can obtain usable text from their own speech without having to purchase every layer of the technology stack.

> **Capture first. Interpret later.**

> **The device should not determine who gets to use the intelligence.**