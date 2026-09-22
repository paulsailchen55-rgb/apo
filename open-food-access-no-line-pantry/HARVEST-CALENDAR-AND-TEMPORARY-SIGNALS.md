# Harvest Calendar & Temporary Food Signals

## Status

**PROPOSED / ARCHIVE-STAGE** — Conceptual extension. Not implemented, deployed, or validated.

## Purpose

Develop an open-source, city-by-city harvest intelligence system that combines public ecological observations, community-garden information, authorized fruit-tree and crop records, seasonal patterns, local confirmations, and temporary food-access notifications.

The system should support three participation modes:

1. **Calendar mode:** A person selects a city, neighborhood, garden, crop, or food category and generates a downloadable iCalendar (`.ics`) file or subscribable calendar feed.
2. **Area-specific mode:** A person changes the geographic area and receives a different set of predicted or confirmed harvest events. Neighborhoods may differ because of microclimate, species, variety, planting date, exposure, soil, irrigation, and management.
3. **Today-only mode:** A person sends a request for confirmed food or harvest opportunities available that day. The request can expire after fulfillment or after a defined short period.

## Proposed information sources

Potential sources include:

- Public biodiversity and ecological observation databases, including iNaturalist where its data access and licensing conditions permit use.
- Community-garden and nonprofit-submitted records.
- Authorized property-owner or steward reports for fruit trees and other food-producing plants.
- Crop calendars, phenology records, frost and heat information, and growing-degree-day calculations.
- Local weather and environmental data where legally and technically available.
- Human inspection and harvest confirmations.
- Actual inventory, quantity, quality-review, and distribution records from participating organizations.

The system must document the source, date, geographic precision, confidence, and verification status of each record.

## Forecasts versus confirmations

The system must distinguish at least four states:

- **Observed:** A plant or crop was reported or observed at a particular time.
- **Forecast:** A harvest window is estimated from historical patterns, environmental conditions, and available records.
- **Inspected:** A local person has checked the plant or crop and recorded its current condition.
- **Confirmed available:** Food has been authorized, quality-reviewed, harvested or otherwise made available, and published for distribution.

A forecast must never be represented as proof that food is ready, edible, safe, or available for public collection.

## Two notification categories

### 1. Harvest task alert

Sent to authorized garden staff, stewards, or volunteers:

> A crop or fruit tree may be approaching a harvest window. Please inspect and confirm.

### 2. Food availability alert

Sent to people who have requested temporary information, only after authorized local confirmation:

> Confirmed food is available today in the selected area. See pickup, collection, or distribution instructions.

The system should not disclose the exact location of privately owned food-producing plants unless the owner or steward has expressly authorized that disclosure.

## Calendar behavior

The calendar layer should support:

- Predicted harvest windows rather than only single dates.
- Confidence or status labels such as forecast, inspection requested, inspected, and confirmed.
- Area-specific calendars.
- Crop-, species-, garden-, and food-category filters.
- Downloadable calendar snapshots.
- Optional subscribed feeds that can update when dates change.
- Links or references to current status information without placing personal information in event titles.
- Expiration or withdrawal of outdated events.
- Clear language that calendar dates are estimates unless explicitly marked as confirmed.

Calendar subscriptions may expose metadata to the calendar provider. The project should avoid putting phone numbers, seeker identities, sensitive needs, or unnecessary location information into calendar events or feed URLs.

## Temporary participation and retention

The seeker-facing system should not require an ongoing account or permanent subscription profile.

A proposed flow is:

1. A person sends an SMS request.
2. The system asks for a geographic area, food category, and participation period when needed.
3. The system creates a random temporary token.
4. A protected delivery service temporarily maps the token to the delivery address.
5. Relevant notifications are sent during the authorized period.
6. A response may renew or modify the request.
7. No response does not renew permission.
8. The delivery mapping expires and is deleted according to the documented retention policy.

A token that can be connected to a phone number is pseudonymous, not fully anonymous. The project must use accurate language and document the limits of application-level privacy, including telecommunications metadata retained by carriers or other providers.

Possible participation periods include:

- One day.
- One week.
- A defined harvest window.
- One season.
- A user-selected period.
- A limited annual seasonal research mode, only if its purpose, safeguards, and retention limits are clearly justified.

The shortest useful retention period should be the default. Research and aggregate seasonal analysis must be separated from operational delivery records and must not be used to justify retaining identifiable seeker histories unnecessarily.

## Recurring distribution patterns

The calendar may eventually include recurring patterns in pantry and store-food distribution, such as:

- Regular distribution days.
- Seasonal food availability.
- Recurring community-garden harvest periods.
- Predictable supply or donation cycles.
- Known organizational closure or holiday patterns.

These patterns should be treated as operational observations or forecasts, not guarantees. They must be verified with participating organizations and updated when schedules or supplies change.

## Privacy and safety boundaries

- Do not use continuous GPS tracking.
- Do not require a seeker to reveal a precise home address when a broader area is sufficient.
- Do not expose private-property food locations without authorization.
- Do not encourage unauthorized harvesting or trespass.
- Do not automatically classify a plant as edible or food as safe solely from an observation database or AI inference.
- Require local human confirmation for public harvest and distribution claims.
- Record provenance, uncertainty, and update dates.
- Provide a way to correct, withdraw, or flag inaccurate records.
- Keep food-safety, quality, and recall workflows separate from ecological prediction.

## Open questions

- Which public datasets permit the intended use, redistribution, and derivative mapping?
- What geographic precision is safe and useful for each plant or property type?
- How should species, varieties, cultivars, and common names be normalized?
- How should the system represent staggered ripening and multi-day harvest windows?
- How should weather and growing-degree-day models be calibrated locally?
- How should calendar feeds be revoked or updated without identifying the subscriber?
- What is the minimum retention period for delivery, safety, and accountability needs?
- How should recurring pantry and store-food patterns be collected without profiling individuals?
