# Stage 1 — Foundation Decisions

**Project:** Civic Two-Minute Ideas / Civic Communication Lab  
**Status:** Proposed — Stage 1 established  
**Evidence classification:** PROPOSED, based on user-directed design decisions  

## 1. Purpose of Stage 1

Stage 1 defines who the system serves, how a person may begin, how much AI assistance may be used, and which outcomes may be produced.

The system should support different levels of experience without requiring every person to follow the same workflow. A person may need basic orientation, help organizing an idea, or a faster process for an already experienced civic participant.

## 2. Primary User Groups

The system must support all of the following:

1. **New participants:** People with little or no experience speaking to public officials or participating in civic meetings.
2. **Idea holders:** People who have an idea, concern, observation, or proposal but need help separating, organizing, and expressing it.
3. **Experienced participants:** People who already understand civic participation and want an efficient process for preparing, checking, or adapting a communication.

The interface should not assume literacy level, technical skill, prior civic knowledge, available time, or confidence. Plain-language explanations and optional advanced detail should coexist.

## 3. Entry Methods

A user may begin through any of these paths:

- Select an existing APO project or archived idea.
- Type a new idea.
- Speak a new idea for transcription.
- Upload a document, handwritten page, photograph, or other supported source.
- Combine multiple entry methods.

The system should preserve the original input and distinguish user-provided material from AI-generated organization or interpretation.

## 4. AI Assistance Modes

The system must support all three modes:

### A. AI drafts first, user reviews

The user supplies an idea or source material. The system organizes the material and proposes a draft for the user to inspect, revise, accept, or reject.

### B. Collaborative development

The system and user work together through questions, alternatives, source checks, and revisions. The user may make decisions at each major stage.

### C. User writes first, AI assists afterward

The user creates an initial draft, including a handwritten draft. The system may transcribe, organize, check, explain, or suggest revisions while preserving the original version and the user's voice.

No assistance mode should be treated as mandatory. The user must be able to change modes during the process.

## 5. Possible Outcomes

All outcomes are available, but each should be optional:

- A concise civic speech or public comment.
- A printable document or formatted handout.
- A practice or rehearsal session.
- A short introduction or 30-second version.
- A two-minute core version.
- An expanded version appropriate to the applicable meeting or communication setting.
- Supporting notes, source references, questions, and follow-up actions.

The system should not force practice, public posting, recording, or submission. It should explain which steps are optional and which requirements come from the relevant meeting or agency.

## 6. Initial User-Controlled Flow

A flexible default flow is:

1. Choose or provide source material.
2. Identify and separate distinct ideas.
3. Clarify the intended audience, jurisdiction, and purpose.
4. Select the desired level of AI assistance.
5. Verify relevant current official sources when external verification is available and implemented.
6. Generate or revise one or more communication outputs.
7. Review and approve the content.
8. Optionally practice, print, export, or prepare follow-up material.

Users may return to earlier steps, skip optional steps, or stop after producing a draft.

## 7. Accessibility and Human Control Requirements

- Use plain-language explanations alongside technical or procedural detail.
- Do not assume the user knows civic terminology.
- Preserve original user input, including handwritten or spoken material when technically supported.
- Clearly label AI suggestions, user-authored text, verified facts, calculations, and unresolved questions.
- Require meaningful user review before content is submitted or publicly shared.
- Avoid claiming that an AI-generated communication will produce a particular official or public response.
- Do not require a user to record audio, upload sensitive information, or publish personal details merely to use the basic workflow.

## 8. Open Questions for Stage 2

- Which user profile should the first prototype display by default?
- Should the system ask a short onboarding question or show all entry methods immediately?
- What minimum information is required before source verification begins?
- How should the system handle users who provide several unrelated ideas in one submission?
- Which features can operate locally in the HTML prototype, and which require a connected AI or retrieval service?

## 9. Decision Record

Stage 1 decisions were provided by the project initiator:

- Primary user: all defined user groups.
- Entry methods: all defined entry methods.
- AI assistance: all three assistance modes.
- Outcomes: all listed outcomes, with optional steps.

These are design decisions for the proposed system, not claims that the implementation has already been built or tested.
