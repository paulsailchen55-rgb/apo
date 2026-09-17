# Architecture

## High-level flow

```text
PERSON
  |
  v
PERSONAL EDGE AGENT
  |
  +--> ORIGINAL INPUT + PROVENANCE
  |
  +--> LOCAL REVIEW / CORRECTION
  |
  +--> USER-AUTHORIZED TRANSFER
          |
          +--> legal / contract analysis
          +--> medical / scientific research
          +--> workplace / union analysis
          +--> government procedure analysis
          +--> general-purpose AI
          |
          v
      EDGE AGENT
          |
          v
   HUMAN REVIEW / APPROVAL
          |
          +--> CONCURRENCE
          +--> NON-CONCURRENCE / DISPUTE
          |
          v
   COLLECTIVE / INSTITUTION
```

## Personal edge agent

The personal edge agent is the user's control plane and custodian. It does not have to be the smartest model in the system. Its primary responsibilities are custody, permissions, provenance, routing, and user control.

"Always available" does not mean "always listening." Capture, processing, and transmission should be explicit states with visible permissions.

### Edge responsibilities

- capture original input
- preserve the original artifact
- hash and encrypt where appropriate
- transcribe locally when feasible
- identify uncertainty
- present the interpretation for review
- record corrections
- decide what information may leave the device
- request authorization before consequential remote transmission
- retain provenance for transformations and transfers
- provide export and exit capabilities

## Modality independence

The input layer should not assume that speech is the only form of human communication. It should support, as applicable:

- speech
- text
- keyboard input
- AAC and assistive devices
- gesture or other accessible input
- documents
- images
- audio recordings
- structured data

The source artifact should remain distinct from every derivative representation.

Example:

```text
audio.wav
   |
   +--> transcription
           |
           +--> structured interpretation
                   |
                   +--> institution-specific document
```

A transcript is not the audio. A structured interpretation is not the transcript. A final institutional document is not the person's original statement.

## Delegated remote AI

Remote AI systems are collaborators operating under authorization from the personal agent. A legal-analysis model, contract analyzer, research model, workplace model, or general-purpose model should receive only the information necessary for its authorized task unless the person explicitly authorizes more.

The personal agent should be able to answer:

- What was sent?
- To which system?
- For what purpose?
- Under whose authorization?
- What came back?
- What transformations occurred?
- What information was retained or returned?

## Replaceability

AI should be replaceable; the person's ledger should not be.

The durable layer should therefore be based on portable records, open formats where practical, documented provenance, user-controlled authorization, and exportable history rather than dependence on one model provider.
