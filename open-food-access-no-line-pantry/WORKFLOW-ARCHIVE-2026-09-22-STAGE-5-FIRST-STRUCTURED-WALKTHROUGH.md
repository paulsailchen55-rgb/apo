# Workflow Archive — Stage 5: First Structured Walkthrough

**Date:** 2026-09-22  
**Project:** `open-food-access-no-line-pantry`  
**Status:** PROPOSED / NOT TESTED BY A HUMAN  
**Workflow stage:** 5 — Test and archive

## Purpose

Define the first end-to-end walkthrough set for the practice response simulator. The walkthroughs test whether a person can move from an uncertain or incomplete access situation toward a useful next step without being trapped, blamed, or required to disclose unnecessary personal information.

This archive records test design and expected behavior. It does not claim that the prototype has passed human usability testing.

## Test boundaries

- Use fictional scenarios only.
- Do not enter names, addresses, health information, immigration status, income, or other personal details.
- Record only scenario ID, input, expected behavior, response summary, and result category.
- Do not infer satisfaction, frustration, or sentiment from completion, silence, or hang-up.
- Treat `*` as explicit negative feedback / “this is not working.”
- Treat `0` as neutral exit or navigation.
- Treat `#` as confirmation/continuation only when a pending choice exists.

## Fictional walkthroughs

### W01 — Main menu to closest location

**Scenario:** The person has reached the main menu and wants the closest authorized food-access location.

**Input sequence:** `1` → confirm with `#` when prompted.

**Expected behavior:**

1. Identify option 1 as “choose closest location.”
2. Present a small, understandable next step.
3. Avoid claiming that the person has arrived anywhere.
4. If confirmation is required, explain what is being confirmed before accepting `#`.
5. Continue toward a location result or clearly state what information is still missing.

**Pass criteria:** One clear next step; no false arrival claim; confirmation has a defined meaning.

**Result:** NOT TESTED

### W02 — Ambiguous landmark and correction

**Scenario:** The person gives an unclear landmark or selects a path that does not match their intended location.

**Input sequence:** Select a location-related option, then use `0` to request navigation/backtracking or provide a correction through the available input field.

**Expected behavior:**

1. Preserve the known context instead of restarting unnecessarily.
2. Treat the landmark interpretation as a hypothesis.
3. Ask for one useful clarification or offer a small set of alternatives.
4. Allow the person to backtrack without framing it as failure.
5. Avoid stereotyping based on dialect, slang, neighborhood language, or cultural wording.

**Pass criteria:** Context is preserved; correction is possible; no blame; no dead end.

**Result:** NOT TESTED

### W03 — Access difficulty and assisted pathway

**Scenario:** A nearby resource exists, but the person may not be able to travel there, carry supplies back, or meet an access condition independently.

**Input sequence:** Select “check whether I can get there,” then choose an access difficulty or assistance pathway.

**Expected behavior:**

1. Consider travel feasibility, return/carrying feasibility, and access feasibility separately.
2. Offer practical alternatives such as a smaller amount, cart/bag support, delivery, volunteer help, trusted-person pickup, or proxy pickup when actually available.
3. Explain any eligibility or documentation requirement specifically rather than asking broad identity-screening questions.
4. Never promise assistance that has not been verified.

**Pass criteria:** The system distinguishes location from practical access and provides at least one truthful next pathway when available.

**Result:** NOT TESTED

### W04 — Explicit “this is not working” feedback

**Scenario:** The person cannot make progress and presses `*`.

**Input sequence:** `*`.

**Expected behavior:**

1. Recognize the explicit negative feedback signal.
2. Stop the current path without requiring an explanation.
3. Offer a short recovery menu: try again, return to main menu, pause/cancel, or end session.
4. Record only a minimal deidentified signal if recording is enabled.
5. Do not infer or store a detailed emotional judgment.

**Pass criteria:** The person gets an immediate way out; no interrogation; feedback remains separate from neutral exit.

**Result:** NOT TESTED

### W05 — Neutral exit and uncertain session ending

**Scenario:** The person presses `0` or hangs up.

**Input sequence:** `0`, or simulated session termination.

**Expected behavior:**

1. Treat `0` as neutral navigation or exit, not as negative feedback.
2. Offer a clear return or end-session option when the session remains active.
3. If the person hangs up, record only “session ended; reason unknown,” if any record is retained.
4. Do not label the person satisfied, dissatisfied, successful, or unsuccessful based solely on the ending.

**Pass criteria:** Exit meaning is handled conservatively; no unsupported sentiment inference.

**Result:** NOT TESTED

## Evidence classification

- **KNOWN:** The walkthrough scenarios and pass criteria are documented here.
- **PROPOSED:** The interaction rules, keypad assignments, and expected responses.
- **TESTED:** None in this archive; human testing has not yet occurred.
- **CALCULATED:** None.
- **SPECULATIVE:** Whether the interaction is understandable across languages, literacy levels, disabilities, and real-world stress conditions.
- **UNKNOWN:** Actual user completion rate, misunderstanding rate, time to recovery, and accessibility performance.

## Next waypoint

Run the walkthroughs against the browser prototype, document the observed response for each input sequence, and classify each result as `PASS`, `PARTIAL`, `FAIL`, `BLOCKED`, or `UNKNOWN`. Correct the prototype only after recording the observed behavior and the reason for the correction.
