# Architecture

## Proposed system boundary

The platform is an open-source intermediary between food seekers and participating organizations. It should not require a seeker to install an app or create a commercial-platform account.

### Access channels

- SMS as the primary low-bandwidth channel.
- Optional human-assisted phone access.
- Optional multilingual conversational assistance.
- Optional web interface where appropriate.
- Optional iCalendar (`.ics`) export or calendar subscription for harvest and distribution forecasts.

### Core services

1. Message intake and routing.
2. Minimal contact/reference management.
3. Daily inventory publication.
4. Preference and restriction capture.
5. Order creation and status tracking.
6. Staff review and substitution handling.
7. Pickup-window scheduling.
8. Food-quality concern reporting.
9. Audit and accountability records with data minimization.
10. Harvest observation, forecast, inspection, and confirmation records.
11. Area-specific calendar generation and update handling.
12. Temporary notification permissions and expiration.
13. Optional integration adapters for existing nonprofit systems.

## Harvest intelligence layer

The proposed harvest layer may combine public ecological observations, community-garden submissions, authorized steward records, crop calendars, phenology, weather indicators, growing-degree-day estimates, and local human confirmation.

It must distinguish:

- observed;
- forecast;
- inspected;
- confirmed available.

AI may assist with organizing, mapping, normalizing, and estimating records, but it must not independently declare a plant edible, a harvest ready, or food safe. Public food-distribution notices require authorized local confirmation.

The layer should support two different alerts:

- **Harvest task alert:** for authorized staff, stewards, or volunteers to inspect a possible harvest.
- **Food availability alert:** for people who have temporarily requested information after food has been confirmed and published.

Exact private-property locations must not be disclosed without authorization. The system must not encourage trespass or unauthorized harvesting.

## Calendar and recurring-pattern layer

The calendar system should support downloadable snapshots and optional subscribable feeds. Events may represent forecast windows, inspection reminders, confirmed availability, recurring pantry schedules, seasonal donation patterns, and community-garden cycles.

Calendar records must include status, source, date of observation or update, geographic scope, and confidence where practical. Forecast events must be visibly distinguished from confirmed availability. Feeds should be revocable and updateable without embedding seeker identity or phone numbers in event titles or URLs.

Recurring pantry and store-food patterns should be modeled as organizational or seasonal observations. They must not be used to profile individuals or infer personal need, eligibility, or behavior.

## Privacy requirements

- No GPS or continuous location tracking.
- No advertising trackers.
- No unnecessary address collection.
- Explicit retention and deletion policies.
- Role-based staff access.
- Encryption in transit and at rest where supported.
- Clear separation between operational records and optional research/analytics.
- Temporary notification tokens with defined expiration.
- Accurate distinction between anonymity and pseudonymity.
- Document telecom metadata limitations; the application cannot control all carrier retention.

## Daily Harvest configuration

A participating community garden may configure a same-day workflow:

`inspect → select → quality review → harvest → publish → order → bundle → distribute`

The configuration must include food-safety checks and should not assume that all harvested food is automatically safe or suitable.

## Integration approach

Use documented APIs and adapters rather than tightly coupling the platform to one accounting, logistics, inventory, or business-management vendor. Integrations are optional and must not be required for the basic SMS workflow.

## Non-goals for the first prototype

- No universal replacement for every pantry's existing software.
- No automated medical diagnosis of allergies.
- No assumption that AI can safely make all food substitutions.
- No mandatory identity database beyond what a participating organization legally and operationally requires.
- No automatic public release of precise private-property plant locations.
- No claim that forecast dates guarantee readiness, safety, or availability.
