# Workflow Archive — Harvest Extension and Seasonal Food Understanding

## Archive metadata

- **Project:** Open Food Access & No-Line Pantry
- **Repository:** `paulsailchen55-rgb/apo`
- **Project folder:** `open-food-access-no-line-pantry/`
- **Date:** 2026-09-22
- **Status:** ARCHIVED CONCEPT / PROPOSED
- **Implementation status:** No working software prototype has been built.
- **Archive purpose:** Preserve the conversation's concepts, decisions, boundaries, and unresolved questions for future community development.

## 1. Conversation objective

Extend the Open Food Access & No-Line Pantry concept beyond daily inventory and same-day distribution into a city-by-city harvest intelligence, seasonal calendar, and temporary notification system.

The extension should remain free and open source, usable by nonprofits, community gardens, local stewards, and people seeking food or harvest information. It should not require a seeker to download an app or maintain a permanent commercial-platform account.

## 2. Main concepts captured

### 2.1 City-scale ecological and harvest intelligence

The proposed system could combine:

- Public ecological observation databases, potentially including iNaturalist where permitted by its data access and licensing conditions.
- Public or community-submitted records of food-producing plants and trees.
- Community-garden crop and harvest records.
- Authorized property-owner or steward information.
- Crop calendars, phenology, frost and heat information, and growing-degree-day estimates.
- Local weather and environmental data.
- Human inspection and harvest confirmation.
- Actual food inventory and distribution records.

AI could assist with organizing observations, normalizing plant names, mapping records, identifying patterns, estimating harvest windows, and producing understandable calendar information. AI must not independently declare that a plant is edible, that food is safe, or that a harvest is ready for public collection.

### 2.2 Geographic variation

Harvest timing can vary between cities, neighborhoods, gardens, properties, and microclimates. The system should therefore support area-specific information rather than assuming that one citywide date applies everywhere.

A person could:

- Select a city.
- Select a neighborhood.
- Select a garden or authorized collection area.
- Select a crop, plant, species, or food category.
- Change the area when traveling to another part of the city or region.
- Receive either forecast information or confirmed availability, depending on the request.

Exact private-property locations should not be publicly disclosed without authorization. The system must not encourage trespass or unauthorized harvesting.

### 2.3 Calendar mode

The project could generate:

- Downloadable iCalendar (`.ics`) files.
- Optional calendar subscription feeds.
- Forecast harvest windows rather than only single dates.
- Inspection reminders.
- Confirmed harvest events.
- Seasonal crop and fruiting cycles.
- Recurring pantry and store-food distribution patterns.
- Calendar updates when observations or schedules change.

Calendar entries must clearly distinguish estimated dates from confirmed availability. A calendar event should not cause someone to assume that food is guaranteed, safe, or available unless the event is explicitly marked as confirmed by an authorized local source.

Calendar feeds should avoid embedding phone numbers, seeker identities, sensitive needs, or unnecessary precise locations in event titles or URLs. Calendar providers may retain metadata outside the project's control.

### 2.4 Three participation modes

The system should support multiple levels of participation:

1. **Calendar mode:** A person selects an area and food category and imports a forecast or seasonal calendar.
2. **Area-specific mode:** A person changes the geographic area and receives information relevant to that area.
3. **Today-only mode:** A person asks what confirmed food or harvest opportunities are available today, with no ongoing notification arrangement.

These modes should use the same underlying information system while allowing different levels of persistence and engagement.

### 2.5 Temporary notification model

The proposed SMS model is temporary permission rather than a permanent subscription profile.

Possible sequence:

1. A person texts the service.
2. The service asks for the area, food category, and requested period when needed.
3. The service generates a random temporary token.
4. A protected delivery service temporarily maps the token to a phone number or other delivery endpoint.
5. Relevant messages are sent during the authorized period.
6. A response can renew or change the request.
7. Failure to respond does not automatically renew permission.
8. The temporary mapping expires and is deleted according to a documented retention policy.

Potential periods include one day, one week, a defined harvest window, one season, or another user-selected period. The shortest useful retention period should be the default.

A token that can be linked back to a phone number is pseudonymous rather than fully anonymous. The project must use accurate terminology and acknowledge that carriers and other providers may retain metadata.

## 3. Recurring food-access patterns

The user identified a further possible calendar component: food distribution may have recurring patterns across the year, including pantry schedules, store-food availability, donation cycles, holiday periods, and seasonal community-garden production.

The system could model these patterns as:

- Organizational schedules.
- Seasonal observations.
- Forecasts.
- Known closure or holiday periods.
- Recurring availability windows.

These patterns must not be used to profile individual seekers or infer their need, eligibility, reliability, or behavior. They should be verified with participating organizations and treated as changeable rather than guaranteed.

## 4. Seasonal understanding and connection to land

The user proposed that year-round food availability can weaken practical awareness of seasonal food cycles and the relationship between people, land, cultivation, harvest, preparation, and shared food.

The user also raised a concern that routine use of pantry bags or store-based food systems—especially when recipients receive unsuitable or unwanted items—may fail to support food appreciation, choice, and direct understanding of where food comes from. The user specifically connected this concern to how children may learn about food and their relationship to the land.

These points are preserved as the user's observations, concerns, interpretations, and design hypotheses. They are not presented as universal findings or established social-science conclusions.

Proposed implications include:

- Seasonal calendars and plain-language explanations.
- Opportunities for people and children to observe, inspect, harvest, prepare, and share food.
- Food choice rather than automatic distribution of unsuitable items.
- Education that supports curiosity, appreciation, and agency without shame.
- A clear distinction between seasonal education and access to emergency food.
- No requirement that someone participate in educational activities before receiving food.
- No romanticizing of scarcity and no blaming people who need emergency food.

## 5. Operational safety boundaries

The proposed system must distinguish:

- **Observed:** A plant or crop was reported or seen.
- **Forecast:** A harvest window was estimated.
- **Inspected:** A local person checked the current condition.
- **Confirmed available:** Food was authorized, reviewed, harvested or otherwise made available, and published for distribution.

Two alert categories are proposed:

- **Harvest task alert:** Sent to authorized stewards, staff, or volunteers to inspect a possible harvest.
- **Food availability alert:** Sent to temporary participants only after authorized local confirmation.

The system must not:

- Automatically classify plants as edible from mapping or AI alone.
- Treat predicted dates as guarantees.
- Disclose private-property locations without permission.
- Encourage trespass or unauthorized harvesting.
- Claim that the platform guarantees food safety or privacy from telecommunications providers.
- Retain identifiable seeker histories merely for convenience or speculative analytics.

## 6. Evidence and provenance labels

Future documentation should continue to distinguish:

- **KNOWN:** User-described experiences, explicit design requirements, or verified source material.
- **CALCULATED:** Derived technical or operational estimates.
- **TESTED:** Demonstrated through an actual prototype or community trial.
- **PROPOSED:** A design idea not yet implemented or validated.
- **SPECULATIVE:** A possibility requiring research.
- **UNKNOWN:** An unresolved question.

The user's personal experiences and interpretations should remain identifiable as provenance and should not be generalized into factual claims without evidence.

## 7. Decisions recorded in this session

- Keep the work in the project's own folder: `open-food-access-no-line-pantry/`.
- Add a dedicated harvest-calendar and temporary-signals document.
- Add a separate core-understandings document for seasonal awareness, dignity, children's learning, and connection to land.
- Extend the architecture with harvest intelligence, calendar behavior, recurring patterns, and temporary notification permissions.
- Extend the roadmap with calendar export, temporary tokens, recurring distribution patterns, and seasonal education testing.
- Preserve the separate Biblical Foodway interpretation pathway rather than silently merging it into secular or technical claims.
- Do not build or claim a working prototype at this stage.

## 8. Files changed for this extension

- `HARVEST-CALENDAR-AND-TEMPORARY-SIGNALS.md`
- `CORE-UNDERSTANDINGS.md`
- `ARCHITECTURE.md`
- `ROADMAP.md`
- `README.md`
- This workflow archive file.

## 9. Unresolved questions for future sessions

- Which public observation datasets can legally and technically support the intended open-source use?
- How should data licensing and attribution be handled?
- How should plant identity, variety, cultivar, and common names be normalized?
- What geographic precision is appropriate for public versus private locations?
- How should harvest windows be forecast and locally calibrated?
- How should climate variation and changing seasons affect forecasts?
- How should calendar feeds be updated, revoked, and expired?
- What information must be retained for food safety, recalls, accountability, and legal obligations?
- How can recurring food-distribution patterns be modeled without profiling individuals?
- What educational approaches support seasonal understanding without creating barriers or shame?
- How should the system be tested with gardens, pantries, volunteers, and people using basic phones?

## 10. Next recommended discussion

Continue exploring the user's observation that people may experience recurring yearly patterns in receiving pantry food and store food. Determine whether these should be modeled as organizational schedules, seasonal supply patterns, personal reminders, or separate calendar layers. Do not infer individual behavior from aggregate patterns without explicit ethical review and safeguards.
