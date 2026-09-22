# Open Questions

## Status

**UNKNOWN / ACTIVE IMPLEMENTATION QUESTIONS**

These unresolved questions are deliberate boundaries against inventing answers.

## Resource data

1. What is the smallest useful resource-record schema for the first prototype?
2. Which fields are required before a resource can be shown as OPEN / ACTIONABLE?
3. How should stale source documents affect resource status?
4. What verification interval is appropriate for different resource types?
5. Who is authorized to verify, correct, pause, or withdraw a resource?
6. How should conflicting sources be represented without silently choosing one?
7. How should temporary closures and holiday exceptions override recurring hours?
8. How should appointment-only services be represented?
9. How should quantity or inventory uncertainty be represented?

## Document ingestion

10. What document formats should the first uploader accept?
11. How should English/Spanish or multilingual documents be linked as versions of the same source?
12. How should extraction confidence be represented at field level?
13. When should human review be mandatory after extraction?
14. How should source pages/sections be preserved for auditability?
15. How should corrected documents supersede older versions without deleting historical provenance?

## Time and calendar

16. What timezone should each resource use?
17. How should daylight-saving transitions be handled?
18. How should a resource with no published hours be presented?
19. When should a recurring service create a calendar event?
20. How should a one-time visit differ from a recurring reminder?
21. How should calendar events be revoked or updated after a closure?

## Location and access

22. What location precision is necessary for each resource type?
23. How should landmark-only clues be matched and corroborated?
24. What information is sufficient to estimate travel feasibility without collecting a home address?
25. How should walking, transit, carrying capacity, delivery, proxy pickup, and assistance be combined?
26. When should the system ask a travel question instead of making a best-effort access calculation?
27. How should accessibility information be represented when the provider has not supplied it?

## Interaction

28. What is the shortest useful response when only one verified option exists?
29. How should the system present a closed resource when it is the closest option but another resource is open?
30. How should the system recover when a location clue is ambiguous?
31. How should keypad *, 0, #, and hang-up behavior remain consistent across resource states?
32. How should optional voice interaction map onto the same underlying resource state machine?

## Privacy and governance

33. What data must be retained for operational accountability?
34. What data can be deleted at end of day?
35. How should temporary notification tokens be stored and expired?
36. What telecom metadata remains outside application control?
37. What role-based permissions are required for document upload, verification, correction, and withdrawal?
38. What community correction mechanism should exist without exposing a seeker's identity?

## Real-world fixture

39. Which current People First Free Guide version should be the first authoritative source fixture?
40. Which small subset of resources should be modeled first?
41. Which fields can be extracted directly from the guide and which require independent verification?
42. How should the historical January 19, 2025 guide be retained as provenance while avoiding any implication that its schedules are current in 2026?

## Testing

43. What test cases should cover open, closed, unknown, eligibility-restricted, temporary closure, and conflicting-source states?
44. What is the minimum machine-readable fixture needed to test the evaluator?
45. Which interaction-burden measures should be retained after the real resource layer is introduced?
