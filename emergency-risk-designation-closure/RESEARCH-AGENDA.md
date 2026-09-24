# Research Agenda

## Primary research question

**How can emergency-response systems preserve the ability to protect a person without allowing emergency-risk classifications, monitoring, or derived data to become indefinite mechanisms of surveillance or unrelated administrative use?**

## Secondary questions

1. What is the difference between emergency intervention and ongoing case management?
2. What makes an emergency designation expire?
3. Which records need to survive for legitimate continuity of care?
4. Which records should not survive?
5. What is the difference between historical documentation and active risk status?
6. How should AI-generated inferences be governed?
7. How can derived information be corrected or removed?
8. How should data-sharing agreements encode purpose limitation?
9. What incentives cause monitoring systems to expand?
10. What technical mechanisms enforce closure rather than merely recommending it?
11. Can automatic expiration be implemented safely?
12. When is human review required?
13. How should a person know that an emergency designation has ended?
14. Can the person obtain a record of what information was collected?
15. Can the person challenge an inaccurate classification?
16. What should happen to copies held by contractors?
17. What happens when multiple agencies independently retain the same information?
18. How should aggregate public-health analysis be separated from identifiable case information?
19. How can emergency systems be audited for function creep?
20. What metrics measure successful closure rather than continued activity?

## Candidate technical model

A future formal model could represent a case as:

C = (trigger, evidence, authority, purpose, scope, clock, review, status, disposition)

where:

- **trigger** = event creating concern;
- **evidence** = information supporting the concern;
- **authority** = legal/organizational basis;
- **purpose** = narrowly defined safety purpose;
- **scope** = permitted intervention;
- **clock** = time boundary;
- **review** = reassessment mechanism;
- **status** = active, resolved, disputed, reopened, etc.;
- **disposition** = retention, deletion, segregation, or lawful archival.

A resilient system should not allow:

purpose = suicide prevention

to silently become:

purpose = any useful information discovered during intervention.

## Failure-loop model

Potential positive feedback:

RISK SIGNAL → DATA COLLECTION → NEW DATA → NEW INFERENCE → NEW RISK SIGNAL

Potential stabilizing feedback:

RISK SIGNAL → LIMITED INTERVENTION → REASSESSMENT → RESOLUTION → CLOSURE

The research question is which architectural and institutional controls force the second loop when the emergency has ended.

## Possible measurements

If a real system is studied, potential measurements include:

- percentage of cases with documented closure;
- median duration of active designation;
- percentage automatically expired;
- percentage manually renewed;
- number of renewals without new evidence;
- number of secondary-use requests;
- number of corrections;
- number of disputed classifications;
- number of AI-generated classifications;
- number of AI-generated classifications later overturned;
- number of data copies;
- retention duration;
- time between resolution and data disposition.

These are proposed research measures, not measurements of Santa Cruz County.

## Verification boundary

No empirical claim should be made about the county system until the relevant primary documents and, where necessary, governing law/policy are obtained and reviewed.
