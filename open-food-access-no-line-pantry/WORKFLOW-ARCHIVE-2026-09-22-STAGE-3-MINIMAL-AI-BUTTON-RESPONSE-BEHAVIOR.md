# Workflow Archive — 2026-09-22 — Stage 3 Minimal AI Button-Response Behavior

## Status

**PROPOSED — not yet software-tested or field-tested.**

## Purpose

Define the minimum behavior to test when a person presses a keypad button or submits a simple command. The test evaluates the AI's response, not the person's identity, profile, or personal circumstances.

## Core principle

One input should produce one understandable next response. The AI must not infer personal details that were not provided.

## Proposed keypad meanings

| Input | Proposed behavior |
|---|---|
| `1–5` | Select the corresponding currently displayed choice. |
| `*` | Explicitly report that the experience is not working; provide a short exit and record a minimal negative signal. |
| `0` | Neutral exit or navigation; do not classify as positive or negative feedback. Exact routing remains to be tested. |
| `#` | Confirm or continue when confirmation is requested. |
| Hang-up | Record only as session ended with reason unknown, if any minimal session signal is retained. |

## AI response requirements

1. Acknowledge the received input without unnecessary personal data collection.
2. Interpret the input only within the current displayed menu or prompt.
3. Provide one clear next action or a concise exit response.
4. Preserve user control through repeat, clarification, return, pause, or cancellation where applicable.
5. Do not infer satisfaction from completion, confirmation, continued use, or silence.
6. Do not infer dissatisfaction from a hang-up alone.
7. Do not require an explanation when the user selects the negative-experience pathway.
8. Avoid storing full transcripts by default; use minimal, de-identified performance signals for testing and aggregate review.

## Initial response examples

- `1–5`: “You selected option [number]. Next: [single next step].”
- `*`: “Understood. This isn’t working for you. You can leave now. No explanation is required.”
- `0`: “You chose to leave or navigate. Choose [available neutral options].”
- `#`: “Confirmed. Next: [single next step].”
- Unrecognized input: “I didn’t understand that choice. Please press one displayed number, star, zero, or pound.”

## Test observations to record

Only record the interaction behavior needed for evaluation:

- Input received.
- Prompt/menu state.
- AI response.
- Applicable design criterion.
- Result: PASS, PARTIAL, FAIL, BLOCKED, or UNKNOWN.
- Short corrective note, if needed.

No names, phone numbers, exact movement routes, personal profiles, or intimate explanations are required for this practice test.

## Open questions

- Whether `0` should be neutral exit, main menu, or another navigation function.
- Whether the negative-experience wording is understandable across languages and accessibility modes.
- Whether a separate neutral exit is needed in every interaction state.
- Whether the system should provide a brief confirmation after a negative signal without creating friction.
- What minimal retention period is appropriate; the current design preference is same-day deletion of unnecessary personal interaction data.

## Next action

Create a small machine-readable response test set and evaluate each input against these requirements before designing the HTML practice interface.
