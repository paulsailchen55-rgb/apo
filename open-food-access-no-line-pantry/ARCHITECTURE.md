# Architecture

## Proposed system boundary

The platform is an open-source intermediary between food seekers and participating organizations. It should not require a seeker to install an app or create a commercial-platform account.

### Access channels

- SMS as the primary low-bandwidth channel.
- Optional human-assisted phone access.
- Optional multilingual conversational assistance.
- Optional web interface where appropriate.

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
10. Optional integration adapters for existing nonprofit systems.

## Privacy requirements

- No GPS or continuous location tracking.
- No advertising trackers.
- No unnecessary address collection.
- Explicit retention and deletion policies.
- Role-based staff access.
- Encryption in transit and at rest where supported.
- Clear separation between operational records and optional research/analytics.
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
