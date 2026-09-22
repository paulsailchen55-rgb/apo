# Workflow Archive — Stage 1: Cultural Wayfinding and Continuing Journey

**Date:** 2026-09-22  
**Project:** Open Food Access / No-Line Pantry  
**Workflow stage:** 1 — Define the User Experience  
**Status:** PROPOSED / NOT IMPLEMENTED / NOT TESTED

## Purpose

Refine the first complete food-access wayfinding scenario so that it supports multilingual, multicultural, vernacular, capability-aware, location-specific, and continuing-journey interactions.

The system must help a person reach an authorized food-access location using the language and location vocabulary they actually know—not require them to translate their experience into standardized street names or formal language first.

## Core scenario

A person is walking, knows their current location through an intersection, landmark, local reference, spoken description, or neighborhood vernacular, and wants directions to an authorized food-access location. They text or speak to the service. The service interprets the request, presents a very small set of relevant choices, guides the person through a reversible choice path, provides only the information needed for the current decision, and gives precise next instructions.

The interaction remains open to correction, backtracking, continuation, and a next journey. “Completion” is not treated as a rigid claim that the person has permanently reached an endpoint. The system may establish that the person is near or at the relevant location based on the information supplied, then remain available for the next requested step.

## Revised user experience

### 1. Origin and language intake

The user may provide:

- Standard street names or intersections.
- A landmark, business, public building, or visible house number.
- A local neighborhood or block reference.
- Vernacular, slang, code-switching, dialect, or culturally specific expressions.
- A spoken description transcribed into text.
- A description that is incomplete, ambiguous, or not directly represented in a standard address database.

The system should:

- Detect or ask about language when necessary.
- Preserve the user's original wording for interpretation and auditability where appropriate.
- Use multilingual and culturally informed transformation layers to map local expressions to candidate geographic references.
- Maintain an expandable place-name and vernacular dictionary.
- Treat transformations as hypotheses until corroborated by context, known geographic data, or user confirmation.
- Never assume that a culturally specific expression is incorrect merely because it is absent from a formal map.
- Ask a short clarification question when multiple locations are plausible.
- Avoid stereotyping a language community, ethnic group, neighborhood, or speaker.

### 2. Small choice-based destination path

Because the person is contacting the food-access number, the first menu should be small and easy to navigate. The proposed interface is a text-based “choose-your-own-adventure” path rather than a large information dump.

The initial choices may include the previously defined food-access categories, such as:

- Free groceries or food staples.
- Prepared or ready-to-eat food.
- Community or resident-authorized food access.
- Same-day or currently available opportunities.
- Help identifying what is available nearby.

The exact final five-choice menu remains to be approved. Choices must be short, understandable, multilingual where needed, and usable by reply numbers, words, or voice.

The user must be able to:

- Choose a branch.
- Go back one step.
- Return to the main menu.
- Change an earlier answer.
- Request more information only when desired.
- Cancel or pause without being penalized.

### 3. Minimal information first

The system should provide only the information needed for the immediate decision, for example:

- Resource type.
- General location or distance description.
- Current information status.
- Public access point.
- Hours or time limits.
- A material restriction or warning.

More detailed information is available through an optional branch. The system should not force the user through long descriptions before they can decide.

### 4. Capability-aware travel assessment

Travel information is not merely a preference. The system must consider whether the person can successfully travel to the resource and transport the food back to their actual destination.

Relevant capability questions may include:

- Walking distance the person can manage.
- Whether they have a cart, bag, bicycle, mobility device, or other carrying capacity.
- Whether they can carry the expected amount of food on the return trip.
- Stairs, steep slopes, uneven surfaces, crossings, lighting, and other route conditions.
- Whether the person is traveling alone or with assistance, if they choose to disclose it.
- Whether a smaller, closer, lighter, or different resource would be more practical.

Questions should be asked only when they affect the route or resource choice. The system must not demand a medical diagnosis or create an unnecessary personal profile.

The system should distinguish:

- **Route feasibility:** Can the person get there?
- **Return feasibility:** Can the person transport the food back?
- **Access feasibility:** Can the person enter, collect, and leave under the stated conditions?

### 5. Location-specific instruction design

Directions should use the best available evidence and modern human-factors research on following instructions. The instruction system should be tested for clarity, sequencing, cognitive load, ambiguity, error recovery, and location-specific hazards.

Instructions should be:

- Ordered one meaningful action at a time.
- Concrete and observable.
- Based on local environmental features where reliable.
- Written in the user's selected language or supported communication form.
- Consistent in wording for repeated landmarks and turns.
- Specific without pretending to have certainty that the data does not support.
- Adapted to the location and route, not unnecessarily personalized through demographic assumptions.
- Capable of being repeated, shortened, expanded, translated, or spoken aloud.

The system should investigate region-specific instruction attributes, including common landmarks, street layout, crossing patterns, terrain, transit barriers, and locally recognizable references. Such adaptation must be evidence-based and must not be used to stereotype local populations.

### 6. Forward-moving correction and recovery

The correction loop should treat every change, detour, pause, backtrack, or cancellation as part of continued movement toward the user's goal or next chosen goal.

Possible replies include:

- `NEXT`
- `REPEAT`
- `SHORTER`
- `MORE DETAIL`
- `I AM AT THE OTHER CORNER`
- `THE ENTRANCE IS CLOSED`
- `I CANNOT USE STAIRS`
- `I HAVE TOO MUCH TO CARRY`
- `CHANGE DESTINATION`
- `MAIN MENU`
- `CANCEL`

The system should respond constructively, without blame or language implying that the user has failed. A route correction is not necessarily “going backward”; it can be a forward adjustment within a continuing journey.

### 7. Nearness, arrival, and continuation

The system should avoid making unsupported claims that it knows the person has physically arrived. It can say that the person is near a described point, that the route's final instruction has been provided, or that the person has reported being there.

The interaction should not require a forced declaration that the journey is permanently complete. After the user reports being near or at the destination, the system may:

- Provide the final access instruction.
- Ask whether they need help identifying the entrance or pickup point.
- Remain available for a next request.
- Support a new destination or return journey.
- End quietly when the user stops interacting.

## Archival philosophical note: “near the destination”

The user described arrival as a state of nearness rather than a rigid endpoint. The reference to Neary Lagoon is a local and personal illustration of how a place can be understood through nearness, surrounding context, and continued movement. The user also connected this to the idea that people and destinations do not need to be represented as permanently “finished” or fully possessed.

This is preserved as a design-philosophy note, not as a scientific claim about particles, matter, antimatter, or physical arrival. The implementable requirement is that the service should support near-destination confirmation, uncertainty disclosure, and continuation into the next journey.

## Multilingual and cultural interpretation architecture — initial requirements

The future system may require:

1. Language identification and user language preference.
2. Speech-to-text that preserves uncertainty and alternate transcriptions.
3. Vernacular and place-reference dictionaries.
4. Alias and nickname mapping for streets, blocks, buildings, and neighborhood features.
5. Contextual geographic candidate generation.
6. Clarification questions that offer candidate interpretations without forcing formal language.
7. Human/community correction pathways for recurring local terms.
8. Versioning and provenance for dictionary entries.
9. Privacy controls for user-submitted expressions and location references.
10. Safety review against biased, insulting, or overconfident translations.

No dictionary or cultural transformation should be treated as permanently complete. Local language changes, neighborhoods change, and a term may have different meanings in different contexts.

## Evidence labels

- **KNOWN:** User-approved direction for multilingual, multicultural, vernacular-aware interaction; small reversible choice path; minimal information first; capability-aware travel; location-specific instruction design; forward-moving correction; continuing-journey framing.
- **PROPOSED:** Architecture and interaction requirements described in this archive.
- **CALCULATED:** Future route and carrying-feasibility calculations, once data and rules are selected.
- **TESTED:** None yet.
- **SPECULATIVE:** The specific techniques and data sources that will produce reliable vernacular-to-location transformations.
- **UNKNOWN:** Supported languages, local dictionary governance, geographic coverage, accuracy thresholds, route engine, and evaluation dataset.
- **NOT IMPLEMENTED:** All software, dictionaries, routing integration, and field testing.

## Stage 1 gate

Stage 1 is not fully closed yet. The primary scenario and major experience principles are documented. Remaining Stage 1 decisions:

- Approve the exact initial small-choice menu.
- Define the minimum clarification behavior for ambiguous local references.
- Define the first capability question set.
- Select the first test location and a small set of realistic language/vernacular examples.
- Define what counts as sufficient instruction clarity for the first prototype.

## Next stage

After the remaining Stage 1 decisions are approved, proceed to **Stage 2 — Design the AI Workflow**, beginning with the interpretation chain:

`User language or speech → transcription/normalization → vernacular and place-reference candidates → geographic clarification → destination choice → capability check → route calculation → concise instruction sequence → correction and continuation loop`.
