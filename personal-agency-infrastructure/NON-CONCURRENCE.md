# Non-Concurrence

## Principle

**Immutable should not mean unquestionable.**

A historical record may need to remain preserved while the person affected by the record disputes its accuracy, interpretation, attribution, or completeness.

The system should therefore support preservation without forced agreement.

## Model

When a person disputes a record, preserve the original artifact and attach a separate non-concurrence record.

A non-concurrence record can contain:

- the original statement or record being disputed
- the person's account
- what specifically is disputed
- the date and author of the disagreement
- supporting evidence, if any
- whether the dispute has been reviewed
- whether a correction was made
- whether the matter remains unresolved

Possible states:

- unresolved
- contested
- corrected
- superseded

The historical artifact should remain identifiable even when a correction is accepted.

## Example

Original record:

> Patient stated X.

Person's non-concurrence:

> I did not say X. I said Y.

The system should preserve both statements and their provenance. It should not silently rewrite the historical record, nor should downstream users automatically treat the original interpretation as uncontested fact.

## Three dimensions of truth

The system should distinguish at least three questions:

1. **Provenance truth** — What artifact exists?
2. **Attribution truth** — Who said, changed, generated, or approved it?
3. **Epistemic status** — What kind of claim is it?

Useful epistemic classifications include:

- direct observation
- reported experience
- interpretation
- allegation
- hypothesis
- verified fact
- disputed
- unknown

This separation prevents an immutable record from acquiring unwarranted certainty merely because it is stored permanently.
