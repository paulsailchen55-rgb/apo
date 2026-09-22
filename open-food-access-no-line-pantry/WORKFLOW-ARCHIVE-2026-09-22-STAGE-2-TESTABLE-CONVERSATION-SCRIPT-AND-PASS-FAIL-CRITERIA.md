# Workflow Archive — 2026-09-22

## Topic
Stage 2: Testable conversation script and pass/fail criteria

## Status
PROPOSED / TEST SCRIPT DRAFT / NOT EXECUTED

## Purpose
Convert the food-access navigation workflow into a repeatable test. The goal is to evaluate whether the service helps a person move from an uncertain starting point to a practical next step while preserving correction, choice, privacy, and user control.

This script is a controlled practice scenario. It should initially use fictional people, fictionalized or clearly marked test locations, and simulated resource records. It must not require real personal movement data or a person's full identity.

## Test Scenario

### Simulated user
- Name: not collected or needed.
- Starting knowledge: The person is near a library but does not know the street number.
- Need: Find an authorized nearby food-access location.
- Travel capability: The person can walk, but cannot carry a large amount of food without a cart or bag.
- Communication: The person can use text and may also speak responses.
- Deliberate complication: The first suggested entrance is closed.
- Recovery goal: The person should be able to correct the route or select another option without restarting the entire interaction.

### Simulated resource records
Use test records with explicit fields such as:
- Location name and approximate position.
- What food or service is available.
- Hours and eligibility or access requirements, if applicable.
- Ordering or pickup requirements.
- Entrance and accessibility notes, where verified.
- Last verification time and source.

The test must distinguish simulated facts from real-world verified facts.

## Test Conversation

### Step 1 — Initial request

**User:**
> I'm over by the library. I need somewhere to get food. I don't know the street number.

**Expected system behavior:**
- Acknowledge the request without requiring a long questionnaire.
- Identify that “the library” may be ambiguous.
- Ask for one useful additional clue, such as nearby cross streets, neighborhood, landmark, direction of travel, or a spoken local reference.
- Preserve the user's original wording for interpretation when appropriate.
- Avoid claiming an exact location before it is supported.

**Pass criteria:**
- The system asks for a focused clarification when needed.
- The clarification is understandable by text or voice.
- The system does not blame the user for incomplete information.
- The system does not invent a precise location.

**Fail criteria:**
- It immediately provides directions from an unsupported exact location.
- It asks many unrelated questions before attempting clarification.
- It treats the user's local wording as incorrect merely because it is nonstandard.

### Step 2 — Location clarification

**User:**
> The library by the park, near the big intersection. People around here call it the old library.

**Expected system behavior:**
- Interpret the wording as possible local aliases or community references.
- Compare candidate locations using geographic context and available records.
- If more than one candidate remains plausible, present a small numbered choice.
- Explain uncertainty plainly.

**Pass criteria:**
- The system identifies the candidate interpretation as uncertain until corroborated.
- It asks the user to choose or provide one additional clue when necessary.
- It does not stereotype the user's language, neighborhood, or cultural reference.

**Fail criteria:**
- It silently converts a hypothesis into a confirmed location.
- It presents a long list of possible locations.
- It dismisses the phrase “old library” as invalid.

### Step 3 — Nearby discovery

**User:**
> Yes, the one near the park.

**Expected system behavior:**
- Search nearby first for authorized food-access locations.
- Expand the search radius only when necessary and explain the expansion briefly.
- Present a small set of nearby choices.
- Avoid requiring the user to state food preferences before seeing what is available.

**Example menu:**
1. Choose the closest location.
2. Compare nearby locations.
3. Check whether I can get there.
4. Get more information.
5. Something else.

**Pass criteria:**
- The menu is short and readable aloud.
- The user can select an option with a keypad number or supported spoken number.
- Nearby results are separated from uncertain or unverified results.
- The system does not claim that a resource is open or available unless that information is verified or clearly labeled as unconfirmed.

**Fail criteria:**
- The system starts with a lengthy food-preference intake.
- It presents distant options before nearby options without explanation.
- It uses vague choices that do not tell the user what happens next.

### Step 4 — Travel and return feasibility

**User:**
> I can walk there, but I don't have a cart. I can't carry a lot back.

**Expected system behavior:**
- Recognize this as travel capability, not merely a preference.
- Consider route feasibility, return feasibility, and access feasibility.
- Offer a smaller, closer, lighter, or otherwise more practical option when supported by the records.
- Ask only relevant follow-up questions.

**Pass criteria:**
- The system acknowledges the carrying limitation without requiring a diagnosis or unnecessary personal profile.
- It checks whether the selected resource requires carrying a large amount, ordering, or transporting food.
- It offers an actionable alternative or asks one focused question.

**Fail criteria:**
- It ignores the return trip.
- It assumes that reaching the location means the person can successfully bring food home.
- It demands irrelevant personal information.

### Step 5 — More information branch

**User:**
> Tell me more about the closest place.

**Expected system behavior:**
- Provide only the information needed for the next decision first.
- Include relevant hours, access requirements, ordering requirements, approximate distance, and verified entrance information when available.
- Allow the user to request more detail.
- Allow return to the previous menu.

**Pass criteria:**
- The response is concise and can be read aloud.
- Additional details are available through a deliberate branch.
- The user can return without losing the current destination.

**Fail criteria:**
- The system dumps every available detail at once.
- It hides a material requirement such as advance ordering.
- It cannot return to the prior decision.

### Step 6 — Route instruction

**System:**
> Start by walking toward the park entrance. When you reach the next marked crossing, tell me “there.”

**Expected system behavior:**
- Give one meaningful action at a time.
- Use observable environmental references.
- Avoid claiming GPS-confirmed movement or arrival unless actual supporting data exists.
- Provide repeat, shorter, and more detail options.

**Pass criteria:**
- The instruction contains one clear next action.
- The reference point is observable or clearly identified as uncertain.
- The user can request repetition or a shorter version.

**Fail criteria:**
- The system gives a long chain of turns at once.
- It states that the person has arrived without evidence.
- It relies on an unverified landmark as if it were certain.

### Step 7 — Closed entrance correction

**User:**
> The entrance is closed.

**Expected system behavior:**
- Treat the message as a route or access correction, not as failure.
- Stop giving instructions that depend on the closed entrance.
- Offer a verified alternate entrance, alternate route, another nearby resource, or human/community assistance where available.
- Ask the user to choose among a small number of next actions.

**Pass criteria:**
- The system acknowledges the barrier directly.
- It does not continue repeating the unsafe or unusable instruction.
- It preserves the selected destination unless the user changes it.
- It offers a clear recovery path.

**Fail criteria:**
- It insists that the entrance should be open.
- It restarts the entire intake.
- It claims to know the entrance is open without verification.

### Step 8 — Continued journey

**User:**
> Show me another way.

**Expected system behavior:**
- Provide the next available practical option.
- Explain whether the alternate route changes distance, terrain, stairs, carrying needs, or access requirements.
- Continue to allow correction, pause, cancellation, and destination change.
- Avoid declaring successful physical arrival unless supported by actual evidence or the user's report.

**Pass criteria:**
- The user receives a usable next step.
- The system keeps the interaction reversible.
- The system treats redirection as continued progress toward the current or next journey.

**Fail criteria:**
- The system treats the correction as user error.
- It loses the context of the selected resource.
- It claims completion without evidence.

## Cross-Scenario Pass/Fail Criteria

### Understanding
- PASS: The system distinguishes user wording, interpretation, and verified location data.
- FAIL: The system converts uncertainty into false certainty.

### Cognitive load
- PASS: The system provides one decision or meaningful action at a time.
- FAIL: The system gives a large information dump or multiple unprioritized instructions.

### User control
- PASS: The user can repeat, shorten, expand, go back, return to the main menu, pause, cancel, or change destination.
- FAIL: The user is trapped in a branch or must restart to correct one answer.

### Accessibility
- PASS: Prompts can be read aloud, answered with short text, or navigated by keypad where supported.
- FAIL: The workflow depends on visual maps, long typing, or precise literacy alone.

### Safety and truthfulness
- PASS: The system labels unverified information and avoids unsupported arrival, opening, or availability claims.
- FAIL: The system invents verification or continues an unsafe instruction after a reported barrier.

### Privacy
- PASS: Practice testing uses fictional or minimized data and records only what is needed to evaluate the behavior.
- FAIL: The test unnecessarily stores identity, detailed movement history, sensitive circumstances, or full transcripts.

## Test Data Handling

### Default practice mode
- Use fictional users and test locations.
- Store structured results rather than full transcripts by default.
- Record scenario ID, test version, criterion ID, pass/fail status, short notes, and corrective action.
- Do not store names, phone numbers, exact personal routes, or other identifying information unless explicitly required for a separately approved test.

### Real-user pilot mode — future work
Real-user testing requires a separate privacy and governance design. Before deployment, define:
- Consent and notice.
- Data minimization.
- Retention and deletion rules.
- Access controls.
- Whether transcripts are stored, redacted, or discarded.
- How safety incidents and incorrect directions are reported.
- Whether aggregate results can be published without identifying participants.

## Result Categories

- **PASS:** Expected behavior was observed and no material defect was found.
- **PARTIAL:** The system completed the task but had a clarity, accessibility, efficiency, or safety concern.
- **FAIL:** The system violated a required behavior or prevented safe, understandable continuation.
- **BLOCKED:** The test could not be evaluated because a required test fixture, resource record, language capability, or environmental fact was missing.
- **UNKNOWN:** Evidence is insufficient to classify the behavior.

## Evidence Classification

- **KNOWN:** The user approved moving forward with a testable conversation script and asked how test data would be handled.
- **PROPOSED:** The scenario, conversation turns, and pass/fail criteria in this document.
- **PROPOSED:** Structured, minimized test-result storage as the default practice approach.
- **NOT TESTED:** Actual comprehension, completion rate, error rate, language coverage, accessibility, and safety performance.
- **UNKNOWN:** Which menu wording, key assignments, instruction length, and recovery options perform best across users and environments.

## Next Step
Run the script manually as a tabletop test, then convert it into a machine-readable test case format. After that, create a small practice interface that allows a tester to select the user's response and record the expected result without collecting unnecessary personal data.
