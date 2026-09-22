# Workflow Archive — Overall Experience Feedback and Privacy Minimization

**Date:** 2026-09-22  
**Project:** `open-food-access-no-line-pantry/`  
**Workflow position:** Stage 3 preparation; feedback and exit control requirement discovered after Stage 2 focus pass  
**Status:** PROPOSED; not yet implemented or user-tested

## 1. Core requirement

The service must provide a simple way for a person to express an overall experience judgment and leave immediately, without being required to explain themselves.

The person may feel:

- The experience was unacceptable or harmful.
- The experience was useful or acceptable.
- The experience was mixed, confusing, or difficult to interpret.

The system must not require a narrative explanation, intimate personal information, or continued conversation.

## 2. User-facing control

A concise overall-experience control should be available at appropriate points, especially when the person wants to exit. It should not interrupt every decision step.

Possible neutral labels for testing:

- `Not acceptable`
- `Acceptable`
- Optional: `Exit without feedback`

The project may test more direct or culturally natural wording, but the underlying meaning must be documented separately from the visible label.

The design must support localization, slang, sarcasm, and community-specific interpretations without assuming that sentiment can be inferred reliably from wording alone.

## 3. Immediate exit behavior

When the person selects the negative experience control:

1. Stop the active interaction unless the person explicitly chooses to continue.
2. Do not argue, defend the system, or ask why.
3. Do not force a survey or personal disclosure.
4. Show a short acknowledgement, if appropriate.
5. Record the minimal feedback event.
6. Apply the configured retention/deletion policy to the associated interaction data.

## 4. Minimal feedback record

The initial record should contain only what is necessary for system improvement, such as:

- Anonymous event identifier or rotating non-identifying batch identifier.
- Date/time bucket rather than exact timestamp where possible.
- Software/workflow version.
- General stage or interaction state, not a full transcript.
- Selected feedback signal.
- Whether the user exited.
- Optional technical failure category if automatically available without collecting personal content.

Do not automatically store names, phone numbers, exact routes, exact locations, intimate answers, or full conversation transcripts.

## 5. Daily review and human-readable summaries

A scheduled review process may group feedback events into a daily internal report for human review. The report should present patterns, not expose individual users.

Example summary categories:

- Repeated location misunderstanding.
- Too many steps.
- Unclear button or prompt.
- Incorrect or unavailable resource information.
- Delivery or assistance pathway failure.
- Accessibility barrier.
- Language, dialect, or translation issue.
- Privacy or trust concern.
- Unknown cause.

The AI may propose a draft summary, but humans must review proposed corrective actions. The system must not rewrite negative feedback into praise or treat sarcasm as confirmed sentiment.

## 6. Sarcasm and interpretation

A negative or positive phrase may be sarcastic, culturally specific, or ambiguous. Therefore:

- Treat the selected control as the user’s explicit signal for that event, not proof of their broader attitude.
- Do not infer sarcasm unless separately tested and clearly marked as uncertain.
- Preserve aggregate counts without pretending to know the person’s emotional state.
- Provide an `UNKNOWN` or `AMBIGUOUS` classification when language-based interpretation is used.

## 7. Privacy and deletion principle

The default design should minimize data collection and avoid retaining unnecessary personal interaction data.

The project must define, before real-user pilots:

- What is retained.
- What is deleted immediately or at the end of the day.
- Whether any de-identified aggregate statistics remain.
- Who can access review reports.
- How deletion is verified.
- How users are informed in plain language.

A daily AI review must not become a justification for retaining full transcripts. If a transcript is not needed, it should not be retained. If temporary data is required for safety or debugging, the purpose, duration, access controls, and deletion process must be explicit.

## 8. Evidence classification

- **KNOWN:** People may want to give blunt feedback without explanation; sarcasm can reverse literal meaning.
- **PROPOSED:** Simple overall feedback control and immediate exit.
- **PROPOSED:** Minimal event record and aggregate daily review.
- **UNKNOWN:** Best user-facing wording across languages and communities.
- **UNKNOWN:** Appropriate retention period and deletion verification method.
- **NOT TESTED:** Whether the control is easy to find without disrupting the service.
- **NOT TESTED:** Whether users interpret the labels consistently.

## 9. Acceptance criteria

A prototype passes this requirement if:

- A user can leave feedback with one simple action.
- No explanation is required.
- The system does not pressure the user to continue.
- The negative signal is not argued with or reinterpreted as praise.
- The stored event excludes unnecessary personal information.
- The associated data follows an explicit retention/deletion rule.
- Daily review produces human-readable patterns without exposing individual identities.
- Ambiguous or sarcastic language is not presented as certain emotional truth.

## 10. Next step

Carry this requirement into Stage 3 HTML application design as a cross-cutting control, then test it with fictional scenarios before considering any real-user pilot.
