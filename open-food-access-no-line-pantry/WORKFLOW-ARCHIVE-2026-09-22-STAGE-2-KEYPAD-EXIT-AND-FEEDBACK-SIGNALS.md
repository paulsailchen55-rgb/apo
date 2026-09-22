# Workflow Archive — 2026-09-22

## Stage 2: Keypad Exit and Feedback Signals

### Status
**PROPOSED — not yet software-tested or field-tested**

### Purpose
Provide a simple way for a person to leave an interaction and, if desired, signal that the service was not working. Do not require an explanation, personal disclosure, rating narrative, or extended questionnaire.

### Proposed keypad model

| Key | Function |
|---|---|
| `1–5` | Select one of the currently displayed choices |
| `*` | **This isn't working** — record an explicit negative-experience signal and exit the current interaction |
| `0` | Neutral exit or navigation; do not interpret as positive or negative feedback |
| `#` | Confirm, continue, or submit the current choice |

### Important distinctions

The system must distinguish among:

1. Continued interaction or completion — not automatically positive feedback.
2. Neutral exit — no sentiment inferred.
3. Explicit negative feedback — only recorded when the person selects or states the designated negative-feedback action.
4. Hanging up or losing contact — record only as **session ended; reason unknown**.

A star press should not force the person to explain what went wrong. The service may provide a short confirmation such as: “Your feedback was recorded. You may leave now.”

### Feedback record minimization

Default record should contain only:

- Random temporary session identifier.
- Feedback signal type.
- Approximate date/time or reporting period.
- Workflow/prototype version.
- Optional technical context needed to identify a recurring failure pattern.

Do not retain a full transcript, exact route, phone number, name, or unnecessary location history by default. Raw interaction data should be deleted by the end of the day unless a separately justified safety, legal, consent-based, or operational exception is defined and documented.

### Review and reporting

The AI may group de-identified signals into daily human-readable maintenance notes, such as:

- Repeated confusion at a menu step.
- A location record that repeatedly fails.
- An instruction that causes correction requests.
- A delivery or eligibility branch that creates a dead end.
- Accessibility or language interpretation problems reported through the feedback pathway.

Reports must describe observed patterns without identifying individual users. The system must not infer positive sentiment from successful completion, continued use, `#`, or silence.

### Accessibility and language considerations

- Label the function in plain language and translate it appropriately.
- Preserve the explicit signal rather than trying to interpret sarcasm or ambiguous free speech.
- Offer text, speech, and predictable repeated prompts where supported.
- Test whether users understand the difference between neutral exit and negative feedback.
- Test key meanings with multilingual users, people with low vision, people using screen readers or text-to-speech, and people with limited typing ability.

### Pass/fail criteria

- **PASS:** A person can submit negative feedback and exit without explaining.
- **PASS:** The system does not classify hanging up as positive or negative.
- **PASS:** Neutral exit is not treated as a sentiment rating.
- **PASS:** No personal details are required for feedback.
- **PASS:** Daily reports are de-identified and focused on fixable system patterns.
- **FAIL:** The system pressures the person to justify criticism.
- **FAIL:** The system treats completion or continued interaction as positive feedback.
- **FAIL:** The system stores unnecessary personal or movement data.

### Open questions

- Whether `0` should be neutral exit, help, or a combined navigation function.
- Whether the negative-feedback wording should be “This isn't working,” “Bad experience,” or a culturally and linguistically tested equivalent.
- Exact retention/deletion schedule and narrowly defined exceptions.
- Whether feedback confirmation should be silent, textual, spoken, or user-selectable.

### Next step
Proceed to Step 8: test and archive. Convert this proposal into a small keypad test set, run it against the existing end-to-end scenario, record results using PASS/PARTIAL/FAIL/BLOCKED/UNKNOWN, and then move toward the HTML practice interface.
