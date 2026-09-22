# Workflow Archive — 2026-09-22

## Topic
Stage 2: AI workflow design for location-first food access

## Status
PROPOSED DESIGN BASELINE — NOT YET IMPLEMENTED OR TESTED

## Core Purpose
The AI helps a person move from what they know now to a practical next step toward authorized food access. It should reduce cognitive load, preserve user control, expose uncertainty honestly, and support correction without treating correction as failure.

The AI is a guide and interpreter, not an authority that should invent facts, claim arrival without evidence, or make decisions on behalf of the person when the person can reasonably choose.

## Core Workflow

### 1. Receive the request
Accept text or speech-transcribed input. The person may provide:

- A location description.
- A landmark, intersection, address, neighborhood term, or local reference.
- A statement that they need food access.
- A travel-capability concern.
- A language, dialect, slang, or culturally specific expression.

The system should preserve the original wording when useful and should not treat nonstandard language as incorrect merely because it differs from formal address language.

### 2. Interpret the location
Extract possible location clues and classify them as:

- **KNOWN:** directly supplied or reliably verified.
- **INFERRED:** a possible interpretation generated from context.
- **UNCERTAIN:** multiple interpretations remain.
- **MISSING:** a necessary detail has not been supplied.

Use local aliases, neighborhood vocabulary, multilingual interpretation, and cultural/vernacular transformation layers as hypotheses. Do not silently convert an uncertain expression into a precise location.

If ambiguity matters, ask a small clarification question. Offer recognizable alternatives when possible:

> “I found two places that could match. Is it 1 or 2?”

Do not require the person to repeat their description in formal language.

### 3. Establish a search area
Start with the closest practical area around the interpreted location. Expand outward only when:

- No authorized resources are found.
- Available resources cannot meet basic access conditions.
- The person asks for more options.
- The person cannot reach the initially identified locations.

The system should explain expansion plainly rather than silently presenting distant options as if they were nearby.

### 4. Find authorized resources
Return only resources that meet the project's authorization and data-quality requirements. For each candidate, gather only the information needed for the immediate decision, such as:

- Approximate location and route relevance.
- Open/closed status when reliably available.
- What access method is required.
- Whether advance ordering, registration, identification, or other conditions apply.
- Whether the person can reasonably reach and leave the location.
- Whether the person can carry the food back to the intended destination.

Unknown or stale information must be labeled as such. The system must not fabricate hours, inventory, eligibility, accessibility, or availability.

### 5. Present the initial menu
Use the proposed five-choice starting menu:

1. Choose the closest location.
2. Compare nearby locations.
3. Check whether I can get there.
4. Get more information.
5. Something else.

The menu is a starting implementation, not a permanent standard. Branches may overlap. For example, choosing the closest location can lead to more information, travel-capability checks, ordering requirements, directions, correction, or another menu.

### 6. Support decision-sized information
Present one meaningful decision at a time. Avoid dumping every available detail into the first response. Offer expansion commands such as:

- `REPEAT`
- `SHORTER`
- `MORE DETAIL`
- `TRANSLATE`
- `NEXT`
- `MAIN MENU`
- `CANCEL`

The system should make the next action visible or audible and should not force the person to remember a long sequence.

### 7. Check practical feasibility when relevant
Do not assume that distance alone determines whether a location is usable. Distinguish:

- **Route feasibility:** Can the person get to the location?
- **Return feasibility:** Can the person carry or transport the food back?
- **Access feasibility:** Can the person enter, collect, and leave?

Ask only relevant questions. Possible factors include distance, slopes, stairs, crossings, uneven ground, lighting, entrances, carts, bags, bicycles, mobility devices, and carrying capacity. Avoid demanding a medical diagnosis when a practical description is enough.

### 8. Provide directions conservatively
Directions should be:

- One meaningful action at a time.
- Concrete and observable.
- Based on reliable local features.
- Clear about direction changes and crossings.
- Designed for repetition and correction.

The system may say that a person is near a described point, has received the final instruction, or reported being there. It must not claim GPS-confirmed arrival unless that evidence actually exists.

### 9. Handle correction and recovery
Treat correction as normal operation. Support statements such as:

- “I am at the other corner.”
- “The entrance is closed.”
- “I cannot use stairs.”
- “I have too much to carry.”
- “Change destination.”
- “Go back.”
- “I need help.”
- “Cancel.”

The AI should acknowledge the new information, preserve what remains useful, and produce the next practical option. It should not blame the user or describe redirection as failure.

### 10. Close or continue the journey
Do not force a rigid success declaration. The person may:

- Continue toward the selected location.
- Request another instruction.
- Change the destination.
- Pause.
- Cancel.
- Ask for a next journey or another type of assistance.

A session may end with a reported outcome, but the system should distinguish user-reported completion from independently verified completion.

## AI State Model

The workflow should maintain a small explicit state record, conceptually containing:

- Current user wording.
- Interpreted location candidates.
- Confidence and unresolved ambiguity.
- Search radius or area.
- Candidate resources and source timestamps.
- Current selected resource, if any.
- Travel/access constraints volunteered by the user.
- Current menu or instruction step.
- Available recovery actions.
- User language or requested communication mode.

The state should be minimal, purpose-limited, and handled according to privacy and retention requirements. Sensitive information should not be collected merely because it might be useful later.

## Safety and Trust Rules

1. Never invent a location, resource, opening time, eligibility rule, inventory claim, route feature, or accessibility condition.
2. Separate verified facts, interpretations, and unknowns.
3. Ask clarification only when uncertainty materially affects safety or usefulness.
4. Prefer nearby practical options before expanding the search.
5. Do not force unnecessary personal, medical, demographic, or food-preference questions.
6. Preserve user choice and provide a way to change decisions.
7. Make correction, pause, cancellation, and human assistance available.
8. Avoid stereotypes when interpreting language, culture, neighborhood, or dialect.
9. Record provenance and version information for dictionaries, aliases, and transformation rules.
10. Escalate to human or community support when the system cannot safely resolve the request.

## Keypad and Voice Layer

The workflow should support text-first use with optional speech recognition and synthesized speech. After the initial location description, menu navigation should use small numbered choices wherever possible.

A standard phone keypad is the baseline interaction model:

- Number keys select visible or spoken options.
- `*`, `#`, and `0` may provide navigation, confirmation, help, or main-menu functions.
- Exact assignments remain PROPOSED and must be tested for ambiguity, language variation, and accessibility.

The service should repeat prompts predictably and recognize supported spoken number words, including multilingual forms, without assuming every language maps perfectly to one English pronunciation.

## Suggested Processing Loop

```text
Receive input
  -> Interpret language and intent
  -> Extract location and practical constraints
  -> Verify or qualify uncertainty
  -> Ask one clarification if necessary
  -> Search nearby authorized resources
  -> Present a small choice
  -> Perform the selected action
  -> Check for correction or barrier
  -> Update state
  -> Give the next small step
  -> Continue, pause, change, or end by user choice
```

## Evidence Classification

- **KNOWN:** The user approved the overall five-choice starting menu and the location-first approach.
- **KNOWN:** The user wants an open-source baseline that others can modify.
- **PROPOSED:** The workflow and state model described in this document.
- **PROPOSED:** The safety, uncertainty, and correction rules.
- **PROPOSED:** The processing loop and decision-sized information strategy.
- **UNKNOWN:** Performance across languages, dialects, literacy levels, disabilities, neighborhoods, and device types.
- **NOT TESTED:** Menu comprehension, route-instruction success, keypad error rates, speech-recognition accuracy, and recovery effectiveness.

## Stage 2 Deliverables to Develop Next

1. A sample conversation showing the full workflow.
2. A formal intent and state schema.
3. A location-ambiguity test set.
4. A resource-verification and freshness policy.
5. A correction and error-recovery test plan.
6. A human-factors review of prompt length, sequencing, and keypad assignments.
7. A privacy and community-governance design.

## Transition
This document establishes the Stage 2 design baseline. The next work should turn it into a concrete sample conversation and testable state/intent model before building the HTML application.
