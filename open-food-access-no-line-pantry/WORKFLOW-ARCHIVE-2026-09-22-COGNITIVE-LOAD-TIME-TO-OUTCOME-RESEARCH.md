# Workflow Archive — Cognitive Load and Time-to-Outcome Research

**Date:** 2026-09-22  
**Project:** Open Food Access / No-Line Pantry  
**Workflow stage:** Research and design-parameter definition  
**Status:** PROPOSED / PARTIALLY RESEARCHED / NOT YET TESTED

## 1. User Need

The system must account for people who may have limited attention, reduced energy, cognitive overload, interruption, stress, or temporary difficulty concentrating. Examples include a difficult two- or three-day period, exhaustion, distress, or recovery from alcohol or drug use. The system must not assume that a person can complete a long sequence of text prompts.

## 2. Core Design Question

How much interaction burden can a person reasonably manage before the system provides a useful outcome, a clear next action, or a meaningful way out?

## 3. Research Findings So Far

### KNOWN

- Human-computer interaction research identifies reading difficulty, scrolling, hierarchical navigation, technical language, and unfamiliar interaction patterns as barriers for novice and low-literacy users.
- Text-only interaction is not universally accessible. Voice, graphical cues, live assistance, and other alternatives may be necessary.
- Research involving people with opioid use disorder shows that digital messaging can support emotional, informational, and material needs, but the reviewed study does not establish a universal maximum number of messages or prompts.
- Cognitive burden is not determined by message count alone. Message length, number of choices, memory demands, ambiguity, interruptions, and recovery from errors also matter.

### UNKNOWN

- A universal maximum number of text messages that is safe or usable for all users.
- Whether the same interaction limit applies across reading ability, language, fatigue, disability, stress, recovery status, and device type.
- Which outcome should count as the minimum acceptable outcome at each stage of the food-access journey.

## 4. Initial Design Hypothesis

### PROPOSED — requires testing

- Provide a useful orientation or immediate next action within the first 1–3 system messages whenever possible.
- Avoid requiring more than 3 consecutive user decisions without offering a useful intermediate result, pause, return, or alternative route.
- Target a verified resource choice or clear access pathway within approximately 5 user interaction turns when the necessary location information is available.
- If verification cannot be completed quickly, state that limitation and provide alternatives rather than continuing an indefinite question sequence.

These numbers are provisional engineering targets, not established scientific thresholds.

## 5. Measures for Our Data

Record only non-identifying practice data:

- Scenario ID
- Number of system messages
- Number of user inputs
- Time or turn count to first useful outcome
- Time or turn count to verified resource or access pathway
- Number of corrections/backtracks
- Whether the user reached an endpoint
- Result category: PASS / PARTIAL / FAIL / BLOCKED / UNKNOWN
- Brief corrective note

Do not collect names, personal history, exact real-world locations, substance-use history, health details, or full transcripts for practice testing.

## 6. Suggested Acceptance Criteria

### PROPOSED

A scenario passes only if:

1. The user receives a useful action or orientation early.
2. Each prompt asks for one meaningful action.
3. The system does not present unverified resources as real or available.
4. The user can pause, backtrack, cancel, or exit without losing all context.
5. The system provides an outcome or a clearly stated limitation before the interaction becomes unnecessarily long.
6. The interaction remains usable when the user gives short, unexpected, incomplete, or nonstandard responses.

## 7. Research Limitations

The initial sources reviewed are relevant to usability and recovery-support messaging, but they do not directly validate the proposed 1–3 message and approximately 5-turn targets. Further research should examine cognitive load, interruption, low-literacy interaction, accessible design, health-service navigation, and task-based usability testing.

## 8. Next Test

Modify the practice scenarios to count message and turn burden. Repeat W01 and compare:

- Current flow length
- First useful outcome point
- Verification point
- Number of unnecessary prompts
- Whether the system could have offered a result earlier

## 9. Evidence Labels

- **KNOWN:** Relevant usability barriers and need for alternatives are documented in research.
- **CALCULATED:** Turn-count and message-count measures can be calculated from test records.
- **PROPOSED:** Initial interaction targets and acceptance criteria.
- **TESTED:** Not yet tested with participants or a validated usability protocol.
- **SPECULATIVE:** Any claim that a particular universal prompt limit applies to every user.
- **UNKNOWN:** User-specific tolerance thresholds and cross-condition generalizability.

## 10. Source Notes

- Medhi et al., *Designing Mobile Interfaces for Novice and Low-Literacy Users* (ACM TOCHI, 2011).
- Ranjit et al., *Text Messages Exchanged Between Individuals With Opioid Use Disorder and Their mHealth e-Coaches: Content Analysis Study* (JMIR Human Factors, 2023).

