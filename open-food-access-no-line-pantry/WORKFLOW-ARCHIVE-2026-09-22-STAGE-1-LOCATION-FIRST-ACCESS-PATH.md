# Workflow Archive — Stage 1 Amendment: Location-First Access Path

**Date:** 2026-09-22  
**Project:** Open Food Access / No-Line Pantry  
**Workflow stage:** 1 — Define the User Experience  
**Status:** PROPOSED / NOT IMPLEMENTED / NOT TESTED

## Decision: Location first

When a person first contacts the food-access number, the system should begin with the person's current location—not with a detailed food-preference questionnaire.

The service should identify the nearest authorized food-access opportunities first, then expand the search outward only when necessary. Results should be organized by practical proximity and should communicate the information needed for the person to decide.

## Initial interaction

1. The person sends a location using a standard intersection, landmark, address, visible number, local reference, vernacular, or spoken description.
2. The system interprets the location and identifies nearby authorized food-access opportunities.
3. The system presents a very small, reversible choice menu.
4. Each choice gives minimal decision-relevant information, such as:
   - What the location provides.
   - Approximate proximity or local distance description.
   - Current information or availability status.
   - Public entrance or pickup point.
   - Important restrictions or access requirements.
5. The person selects a location or resource and receives directions.
6. More detailed information is available through an optional branch rather than being forced into the first response.

## Food selection versus ordering

The system should not require the person to specify food preferences before showing nearby options. The person can first learn what each nearby resource provides and then choose.

Food selection or ordering becomes relevant only when the selected resource requires it. Examples include:

- A pantry that requires an order before pickup.
- A resource that uses an inventory or request process.
- A location where the person must submit the desired items before arriving.

If the system knows that an order is required before travel, it should disclose that requirement before sending the person away from their current location and provide the appropriate ordering path. The system should describe available items or ordering choices as information about that resource—not as an assumption about the person's general preferences.

## Interface principle

The service should not require a dedicated application. The first implementation should be text-first, with optional voice support where available. The interaction should function through concise messages, reply numbers or words, and reversible branches.

The proposed interaction resembles a small choose-your-own-adventure path:

- Select an option.
- Receive only the information needed for the current decision.
- Ask for more information if wanted.
- Go back one step.
- Return to the main menu.
- Change the selection.
- Continue to directions or ordering.

This is a navigation and decision path, not a conventional visual map requirement.

## Updated workflow sequence

`User-declared location → language/vernacular interpretation → nearest authorized opportunities → small choice menu → minimal resource information → optional ordering requirement → capability-aware route check → directions → correction/continuation`

## Evidence labels

- **KNOWN:** User-approved location-first interaction; nearest opportunities before detailed food preference questions; minimal information first; ordering only when the selected resource requires it; no required app.
- **PROPOSED:** Search-expansion behavior, menu structure, and conditional ordering workflow.
- **UNKNOWN:** Exact initial menu, proximity thresholds, inventory freshness, ordering integrations, and first supported channels.
- **TESTED:** None yet.
- **NOT IMPLEMENTED:** Software, routing integration, ordering integration, and field testing.

## Stage 1 gate impact

This amendment resolves the previous question about whether the system should ask food needs before finding nearby locations: **it should find nearby authorized opportunities first.**

Remaining Stage 1 decisions include the exact small-choice menu, minimum clarification behavior, first capability questions, initial test location, realistic multilingual/vernacular examples, and instruction-clarity criteria.
