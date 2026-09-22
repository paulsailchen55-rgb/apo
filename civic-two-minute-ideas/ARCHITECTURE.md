# Architecture

## Shared pipeline

The system uses a flexible, user-controlled pipeline rather than one mandatory sequence:

**Human-first access prompt** → human phone/text/local-resource options → optional website or HTML tool → optional AI conversation → APO idea or new input → idea separation → source intake → clarification → source retrieval and version comparison when available → jurisdiction and agenda analysis → participation-mode profile → evidence review → core speech or other selected output → optional strategy and Lab suggestions → human review → optional practice, printing, export, or follow-up.

The human-first prompt is a primary entrance, not a fallback. Users may choose human help because they are technologically fatigued, prefer conversation, lack reliable internet, want a local resource, or simply want to develop an idea with another person.

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

## Human support discovery layer

A connected implementation may search current local sources for verified phone, text, in-person, library, nonprofit, civic, or peer-support options. Every displayed resource should include its actual service scope, contact method, location or coverage, accessibility information when available, source, retrieval date, and verification status.

The system must not claim that 211, a library, or another organization offers civic idea development unless that service is confirmed. A possible related project may establish a human civic-idea support network of trained people who help residents clarify ideas and prepare for legitimate participation.

## Two sides

### AI/workflow side

- Prompt and instruction library
- Human-first resource discovery and verification
- Current-source retrieval and source register
- Document comparison and conflict detection
- Idea decomposition and evidence classification
- Agenda and jurisdiction matching
- Speech generation and timing variants
- Communication-fit and ethical strategy guidance
- Public-engagement and follow-up suggestions
- User-profile and assistance-mode selection

### HTML/app side

- Human-first access panel
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
