# Workflow Archive — 2026-09-22

## Topic
Stage 2 practice scenario: ambiguous location, resource selection, barrier, and recovery

## Status
PROPOSED / PRACTICE DESIGN / NOT TESTED

## Purpose
Use a complete hypothetical interaction to expose weaknesses in the AI workflow before building the HTML application. This scenario is illustrative and does not assert that the named resources, hours, routes, or access conditions are currently available.

## Scenario Setup
A person is walking and says:

> “I'm over by the library. I need somewhere to get food. I don't know the street number.”

The system should avoid a long questionnaire. It should first determine whether the location description is sufficiently specific and ask for only the next useful clarification.

## Example Interaction

### 1. Understand the location

**Person:** I'm over by the library. I need somewhere to get food.

**Service:** I can help. Which library do you mean? I found two possible locations nearby.

1. The library near the main shopping area
2. The library near the park

Press 1 or 2. You can also tell me another landmark. Press * to hear this again.

**Design note:** The service does not silently choose one interpretation. It presents a small set of hypotheses and asks for confirmation.

### 2. Confirm and discover nearby resources

**Person:** One.

**Service:** Thank you. I will look near the library by the main shopping area.

I found three authorized food-access locations nearby.

1. Closest location
2. Compare nearby locations
3. Check whether you can get there
4. More information
5. Something else

**Design note:** The menu is contextual. It is not necessarily repeated identically at every stage, but the core functions remain available.

### 3. Choose the closest location

**Person:** One.

**Service:** The closest listed location is approximately [distance estimate] from the library. It may require an order before pickup.

1. Get directions
2. Find out what it provides
3. Check travel and carrying needs
4. Return to nearby locations
5. Something else

**Design note:** More information is available inside the closest-location branch. The system should not force the person to return to the original menu to obtain essential details.

### 4. Check practical feasibility

**Person:** Three.

**Service:** Before you go, I can check practical travel needs. Do you plan to walk?

1. Yes
2. No
3. I am not sure
4. More information
5. Something else

**Person:** One.

**Service:** Can you carry the food back with you?

1. Yes, I have a bag or cart
2. I can carry only a small amount
3. I need help carrying it
4. I am not sure
5. Something else

**Design note:** These questions are asked only when relevant. The service should not require a medical diagnosis or collect unnecessary personal information.

### 5. Provide a route instruction

**Service:** Start by walking toward [reliable local landmark]. When you reach [observable intersection or feature], stop and tell me what you see. I will give you the next step.

**Design note:** Instructions should be incremental, concrete, observable, and recoverable. The system should avoid presenting a long route that assumes the person will follow every step without correction.

### 6. Handle a route correction

**Person:** I'm at the other corner. I don't see the entrance.

**Service:** That's okay. We can adjust from where you are now. Are you facing the library or the street?

1. Facing the library
2. Facing the street
3. I am not sure
4. Repeat the last instruction
5. Something else

**Design note:** The response treats correction as continued progress. It does not blame the person or restart the entire interaction.

### 7. Handle an access barrier

**Person:** There are stairs. I cannot use stairs.

**Service:** Thank you for telling me. I will look for another entrance or another nearby location that may work better.

1. Check another entrance
2. Compare nearby locations
3. Ask for help
4. More information
5. Something else

**Design note:** The system must not promise that an accessible route exists until the relevant information is verified. It should clearly distinguish reported, mapped, and unverified information.

### 8. Continue or change the journey

**Person:** Two.

**Service:** I will compare nearby locations. I will show the closest options first and include any known ordering, entrance, carrying, or access requirements.

The person can continue, change the destination, return to the main menu, pause, or cancel at any time.

## AI Workflow Rules Demonstrated

1. Treat language and location interpretation as hypotheses until corroborated.
2. Ask the smallest useful clarification question.
3. Search locally first and expand outward only when necessary.
4. Present options in a small, keypad-compatible format.
5. Make more-information functions available within branches.
6. Separate route feasibility, return feasibility, and access feasibility.
7. Give one meaningful action at a time.
8. Use observable landmarks and allow the person to report what they actually see.
9. Support correction, backtracking, pausing, cancellation, and destination changes.
10. Never claim confirmed arrival without appropriate evidence.
11. Distinguish verified facts, user reports, system interpretations, and unknowns.
12. Avoid collecting unnecessary sensitive information.

## Failure Conditions to Test Later

- The phrase “the library” matches several locations.
- A local nickname or vernacular reference has multiple possible meanings.
- The location data is outdated or incomplete.
- A resource is listed but closed, moved, or temporarily unavailable.
- A route includes stairs, unsafe crossings, steep terrain, or an inaccessible entrance.
- The person cannot carry the expected amount of food.
- Speech recognition mishears a number, “star,” or “pound.”
- The person changes their mind after several steps.
- The person gives a correction that conflicts with the assumed route.
- The service cannot verify whether a person has arrived.

## Evidence Classification

- **PROPOSED:** The example dialogue and sequence.
- **PROPOSED:** Incremental route instructions and correction behavior.
- **KNOWN:** The user wants location-first access, small reversible choices, travel capability checks, and open-ended recovery.
- **UNKNOWN:** Real-world comprehension, completion, error, and accessibility rates.
- **NOT TESTED:** The menu wording, number recognition across languages, route correction prompts, and barrier handling.

## Next Step
Convert this scenario into a testable conversation script with explicit inputs, expected system behavior, failure cases, and pass/fail criteria. Then use it to guide the AI workflow specification and the first HTML prototype.
