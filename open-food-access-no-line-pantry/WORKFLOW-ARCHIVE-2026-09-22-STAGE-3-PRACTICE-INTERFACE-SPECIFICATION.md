# Workflow Archive — Stage 3 Practice Interface Specification

**Date:** 2026-09-22  
**Project:** `open-food-access-no-line-pantry/`  
**Workflow stage:** 3 — Design the HTML application  
**Status:** PROPOSED; not yet implemented or user-tested

## 1. Purpose

Define the smallest practice interface for testing the AI's response behavior to fictional inputs. The practice interface is not a production food-access service and does not require personal data.

## 2. Core test loop

1. Present a fictional starting situation or menu state.
2. Accept one input: keypad key, short command, or simulated spoken input.
3. Display the AI response.
4. Compare the response with the applicable behavior rule.
5. Record only a minimal test result.

## 3. Minimal interface areas

- **Scenario panel:** fictional scenario identifier and current state.
- **Input panel:** keys `0–9`, `*`, and `#`, plus optional short command input.
- **AI response panel:** one response at a time, with repeatable text.
- **Behavior-check panel:** expected rule, observed behavior, and result category.
- **Reset/next test controls:** restart the current scenario or move to the next test.

## 4. Proposed keypad behavior

- `1–5`: select the currently displayed numbered option.
- `*`: explicit “This isn't working” feedback and exit pathway.
- `0`: neutral exit or navigation; it must not be interpreted as positive or negative sentiment.
- `#`: confirm or continue when confirmation is requested.
- Hang-up/session termination: record only as “session ended; reason unknown” in the test model.

These assignments are PROPOSED and require accessibility, multilingual, and interaction testing.

## 5. AI response rules to test

The AI response should:

- Give one clear next step whenever possible.
- Avoid claiming certainty when the input is ambiguous.
- Preserve the current context when a user corrects or changes direction.
- Offer recovery instead of creating a dead end.
- Avoid asking unnecessary personal or sensitive questions.
- Avoid inferring positive or negative sentiment from completion, continuation, silence, or hang-up.
- Treat explicit feedback signals as signals, without requiring an explanation.
- Keep messages short enough for reading aloud and keypad use.
- Permit repeat, clarification, pause, cancellation, and return to navigation where supported.

## 6. Minimal test-result record

The practice model may record:

- Scenario identifier.
- Test case identifier.
- Input received.
- Expected behavior rule identifier.
- Observed response summary.
- Result: `PASS`, `PARTIAL`, `FAIL`, `BLOCKED`, or `UNKNOWN`.
- Short corrective note.

It should not require names, phone numbers, exact personal locations, personal histories, full transcripts, or a persistent identity.

## 7. Privacy boundary

This is a behavior-testing model. Personal details are not needed. Any future real-user testing requires a separate privacy and governance design, including minimization, retention limits, access control, and deletion procedures.

## 8. Evidence classification

- **KNOWN:** The practice interface is intended to test AI response behavior rather than gather personal information.
- **PROPOSED:** Interface panels, keypad assignments, result categories, and response rules.
- **UNKNOWN:** Whether the proposed key meanings are understood consistently across languages, accessibility needs, devices, and communication modes.
- **NOT TESTED:** No working interface or formal user test has yet been completed.

## 9. Next waypoint

Create the first small practice implementation or interactive mockup using a limited set of scenarios. Test the response loop before expanding the interface.
