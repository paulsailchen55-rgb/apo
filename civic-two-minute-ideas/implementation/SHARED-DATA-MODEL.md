# Shared Data Model

Core records:

- `idea`: title, description, source APO folder, jurisdiction, status
- `evidence`: claim, category, source, confidence, verification date
- `source`: agency, document title, URL, revision date, retrieval date, applicability, status
- `meeting`: body, date, agenda URL, agenda item, participation modes, rules
- `mode_profile`: phone, video, in-person, written, or scheduled meeting requirements
- `speech`: target duration, audience, mode, script, sources, review status
- `strategy_note`: procedural options, uncertainties, and user-selected approach
- `lab_experiment`: concept, purpose, constraints, compliance review, fallback

The AI and HTML app should use compatible field names and preserve provenance across transformations.
