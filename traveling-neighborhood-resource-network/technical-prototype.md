# Technical Prototype

## Product concept

A future application could combine:
- map/search
- host profiles
- resource categories
- approximate locations
- availability
- request/accept flow
- payment
- agreements
- verification
- incident reporting
- jurisdiction information
- privacy controls

The Airbnb comparison is an interface analogy, not a claim that this project should copy Airbnb's business or legal model.

## Minimal non-transactional prototype

Before accepting real money, prototype:
1. Choose a location.
2. Select a resource.
3. Show only approximate host location.
4. Display eligibility questions.
5. Show host rules.
6. Submit a request.
7. Simulate acceptance.
8. Reveal what information would be exchanged.
9. Show a hypothetical checkout.
10. Record what legal/safety questions remain unresolved.

## Jurisdiction engine

A listing could carry structured fields such as:

jurisdiction:
property_authority:
resource_type:
maximum_requested_stay:
parking_status:
overnight_use_status:
short_term_lodging_status:
lease_review_status:
mortgage_review_status:
insurance_review_status:
permit_status:
human_review_required:
source_dates:

These fields are not legal conclusions. They are a way to expose what has and has not been checked.

## API direction

A future API could expose:
- resource availability
- listing metadata
- booking/request state
- verification status
- jurisdiction status
- payment state
- incident status

Sensitive information should not be exposed through a public API merely because it exists in the database.

## Architecture principle

Separate:
- public discovery data
- private host data
- traveler identity data
- transaction data
- legal-source data
- verification data
- incident data

This reduces the consequences of a single data leak.

## Human override

Automated eligibility should never be the only route for unusual or ambiguous cases.

If the system cannot determine whether a host may legally provide a resource, it should say:

**Needs human review.**

It should not manufacture a yes/no answer.
