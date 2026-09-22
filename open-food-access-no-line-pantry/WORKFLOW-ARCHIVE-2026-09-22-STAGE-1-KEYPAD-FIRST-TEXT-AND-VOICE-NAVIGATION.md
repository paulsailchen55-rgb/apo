# Workflow Archive — Stage 1: Keypad-First Text and Voice Navigation

**Date:** 2026-09-22  
**Project:** Open Food Access / No-Line Pantry  
**Workflow stage:** 1 — Define the User Experience  
**Status:** PROPOSED / NOT IMPLEMENTED / NOT TESTED

## Purpose

Define an accessible interaction model for people using ordinary mobile phones, including phones with physical number keypads, text-to-speech, limited vision, limited typing ability, or speech-based interaction.

## Core interaction principle

**One choice, one button, one next step.**

The service must not require users to type long messages, navigate a complex app, or learn an extensive command language. The primary menu and navigation controls should be usable through the standard telephone keypad:

- Number keys `0–9`.
- Star `*`.
- Pound/hash `#`.

The service may also accept spoken number commands and spoken words when voice recognition is available, but speech must not be the only access method.

## Location-first intake

Location is the primary first-stage input. The user may provide their location through speech, a short text, a recognized intersection, landmark, local reference, vernacular, or another supported description. The system should not force the user to type standardized street names when they know a local reference instead.

Because a location description may be longer or more difficult than a menu choice, the system should support a short voice/text intake path for location and then use keypad choices for the rest of the interaction wherever possible.

## Small menu requirements

The menu must:

- Present only a small number of choices at each level.
- Use short, plain language.
- Support numbered responses.
- Support `*` for a defined back/repeat/navigation function and `#` for a defined confirm/submit/continue function, subject to testing and final assignment.
- Include `0` only when its purpose is clear, such as help, operator/community assistance, or return to the main menu.
- Repeat the available choices in a predictable order.
- Permit backtracking and changing an earlier selection.
- Avoid requiring the user to memorize many commands.
- Work with text-to-speech and spoken readout.
- Allow the user to repeat, shorten, expand, translate, pause, or cancel.

The exact keypad assignments remain to be finalized after testing. No key should have different meanings in closely related contexts without an explicit prompt.

## Choose-your-own-adventure structure

The interaction is a small, reversible decision tree rather than a map application. The user selects one option, receives the next small set of options or the next necessary information, and can move backward or return to the main menu.

The initial flow should begin with nearby authorized food-access opportunities, not a mandatory food-preference questionnaire. Food preference or order details are requested only when a selected resource requires them, such as a location that requires an order before pickup.

## Accessibility requirements

The first design must account for:

- Users who cannot see small text clearly.
- Users whose phone reads text aloud.
- Users who cannot type substantial text.
- Users who prefer speaking in their own language or dialect.
- Users who know local vernacular or neighborhood references better than formal addresses.
- Users who need a slow, repeatable interaction.
- Users who may accidentally press a key or need to recover without penalty.

The system should provide concise prompts, predictable numbering, confirmation where an action has meaningful consequences, and an easy repeat function.

## Proposed baseline key roles

These are design candidates, not final assignments:

- Number keys: select the currently displayed option.
- `*`: repeat, go back, or another navigation function to be selected through testing.
- `#`: confirm, continue, or submit the current selection, subject to final design.
- `0`: help, main menu, or human/community assistance, subject to final design.

A single key should not be overloaded with several meanings unless the prompt makes the meaning unambiguous and testing demonstrates that users understand it.

## Evidence labels

- **KNOWN:** User-approved keypad-first interaction using `0–9`, `*`, and `#`; simple one-button progression; support for spoken numbers and text-to-speech; no required app.
- **PROPOSED:** The menu structure, accessibility requirements, and candidate key roles in this archive.
- **UNKNOWN:** Final key assignments, menu wording, language coverage, speech-recognition reliability, and keypad behavior across carriers and devices.
- **TESTED:** None yet.
- **NOT IMPLEMENTED:** No working keypad service or accessible prototype yet.

## Stage 1 gate impact

This decision narrows the first user experience requirements. Stage 1 still requires agreement on:

1. The exact first menu choices.
2. The final roles for `*`, `#`, and `0`.
3. The location-intake format for longer spoken or text descriptions.
4. The first accessibility test scenario.
5. The first test population and test location.

## Next stage implication

Stage 2 must design the AI workflow around two distinct interaction layers:

`Location language/speech intake → interpretation and geographic candidates → keypad-friendly nearby resource menu → selected resource details → capability check when necessary → route instructions → repeat/correction/backtracking → continuing journey`.

The keypad layer should remain simple even if the underlying language interpretation, geographic transformation, and routing systems are complex.
