# Architecture

## Shared pipeline

The system uses a flexible, user-controlled pipeline rather than one mandatory sequence:

APO idea or new input → idea separation → source intake → clarification → source retrieval and version comparison when available → jurisdiction and agenda analysis → participation-mode profile → evidence review → core speech or other selected output → optional strategy and lab suggestions → human review → optional practice, printing, export, or follow-up.

Users may enter at different points, revisit earlier steps, change AI assistance modes, skip optional steps, or stop after producing a draft.

## Stage 1 user model

The architecture supports three overlapping user groups:

- New civic participants who need orientation and plain-language guidance.
- People with ideas or concerns that need separation, organization, and expression.
- Experienced participants who want speed, checking, and adaptable outputs.

Entry methods include selecting an APO project, typing or speaking a new idea, uploading a document or photograph, and combining these methods.

AI assistance supports three modes:

1. AI drafts first, followed by user review.
2. Collaborative development between user and AI.
3. User writes first, followed by AI transcription, organization, checking, or revision assistance.

Possible outputs include a concise speech, printable document, practice session, short version, two-minute core version, expanded version, and supporting notes. Practice, recording, public sharing, and submission are optional unless an external process imposes a specific requirement.

## Two sides

### AI/workflow side

- Prompt and instruction library
- Current-source retrieval and source register
- Document comparison and conflict detection
- Idea decomposition and evidence classification
- Agenda and jurisdiction matching
- Speech generation and timing variants
- Communication-fit and ethical strategy guidance
- Public-engagement and follow-up suggestions
- User-profile and assistance-mode selection

### HTML/app side

- Local project intake form with multiple entry paths
- Upload/import area for source documents and photographs
- Source register and verification status
- Idea cards and evidence labels
- User assistance-mode selector
- Meeting/agenda profile
- Participation-mode selector
- Speech editor and approximate timing display
- Optional practice controls
- Lab sandbox with explicit rule checks
- Export to Markdown, text, and printable HTML

The HTML prototype should not claim to perform live web retrieval unless that capability is actually implemented. It should clearly distinguish locally supplied sources from externally verified sources. It should preserve original user input and separate user-authored material from AI-generated suggestions.
