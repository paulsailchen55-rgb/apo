# Workflow Archive — 2026-09-22 — Stage 6: Interaction Burden Measurement and Verification Order

## Waypoint
Update the browser practice prototype to measure interaction burden and prevent an unverified resource from being presented as a confirmed result.

## KNOWN
- The prior W01 walkthrough exposed an ordering problem: a fictional practice location was introduced before its fictional/unverified status was made explicit.
- The prototype is a deterministic simulator, not a production AI service.
- Practice runs must not request or store personal information.

## PROPOSED
- Count system messages, user inputs, and interaction turns.
- Display first-useful-outcome and verification-point markers.
- Use explicit language such as “hypothesis,” “not confirmed,” “verify,” and “availability will not be promised until verified.”
- Keep the counters as engineering observations rather than claiming a scientifically established maximum number of prompts.

## IMPLEMENTED
- Updated `practice/ai-response-practice.html`.
- Added visible counters for system messages, user inputs, and turns.
- Added first useful outcome and verification point markers.
- Revised scenario responses to avoid presenting unverified resources as confirmed.
- Preserved keypad pathways for neutral exit (`0`), explicit negative feedback (`*`), and confirmation/continuation (`#`).
- Kept minimal behavior categories: PASS, PARTIAL, FAIL, BLOCKED, UNKNOWN.

## TEST STATUS
- `TESTED`: GitHub accepted the file update.
- `UNKNOWN`: Interactive browser execution and accessibility testing still need to be performed in a browser.
- `UNKNOWN`: Whether the current heuristic marker correctly identifies every useful outcome and verification point.

## LIMITATIONS
- The current counter treats each keypad input as one user input, one system response, and one turn.
- The marker logic uses simple text/rule heuristics and is not a validated cognitive-load measure.
- No scientific message-count threshold is asserted.
- Resource verification remains simulated; no live availability provider is connected.

## NEXT WAYPOINT
Repeat W01 in the updated prototype and record:
1. First useful outcome input number.
2. Verification point input number.
3. Total system messages, user inputs, and turns.
4. Whether any fictional/unverified location is presented as confirmed.
5. Whether the user can exit, pause, recover, or change direction without losing context.
