# Countywide GIS Parking Identification and Flexible Parking Leasing — Development and Engagement Plan

## Status

**Classification:** Potential project / civic technology and policy research direction

**Purpose:** Investigate whether parking spaces can be mapped, identified, governed, and voluntarily allocated through time-limited agreements while respecting jurisdiction, privacy, accessibility, and existing road rules.

This is a research and design plan, not a proposal to bypass parking law or authorize access to restricted vehicle data.

## Core Concept

The system could potentially combine:

- A GIS inventory of public and participating private parking spaces
- A unique identifier for each mapped space or space group
- Jurisdictional and zoning overlays
- Applicable restrictions, hours, accessibility rules, and permit conditions
- Voluntary short-term reservations or agreements where legally authorized
- Payment, subsidy, or nonprofit sponsorship options
- Clear records of authorization, duration, and responsibility

## Development Stages

### Stage 1 — Define the Scope and Boundaries

- [ ] Distinguish public curb parking, public lots, private lots, residential streets, accessible spaces, loading zones, and restricted spaces.
- [ ] Define whether the first use case is information-only, reservation, payment, permit support, or a full agreement workflow.
- [ ] Define what a parking-space identifier means and who maintains it.
- [ ] Separate county, city, state, private-owner, and other jurisdictional responsibilities.
- [ ] Record the difference between a parking space, a vehicle, a permit, a reservation, and a legal right to occupy space.
- [ ] Define non-goals, including universal parking entitlement and unrestricted access to DMV information.

### Stage 2 — Existing-System Research

- [ ] Review Santa Cruz city and county parking regulations, permit programs, meters, citations, residential restrictions, and accessible-parking rules.
- [ ] Investigate the citywide permit-parking agenda item as a research lead, locating the agenda packet, staff report, maps, and adopted action if available.
- [ ] Identify existing GIS datasets, curb-management systems, asset inventories, and open-data portals.
- [ ] Determine whether spaces are already numbered or otherwise referenced by agencies.
- [ ] Research California DMV data-access rules and permissible uses of vehicle or license-plate information.
- [ ] Review privacy, public-records, cybersecurity, and data-retention requirements.
- [ ] Compare relevant parking-management and curb-management programs in other jurisdictions.

### Stage 3 — Data and GIS Architecture

- [ ] Define a minimum data schema for a space: identifier, coordinates or geometry, jurisdiction, ownership/control, space type, restrictions, hours, accessibility status, and source date.
- [ ] Establish data provenance and a process for correcting inaccurate or outdated records.
- [ ] Design jurisdictional overlays without implying that GIS alone creates legal authority.
- [ ] Separate public information from restricted operational or personally identifiable information.
- [ ] Evaluate interoperability with existing city, county, transportation, and mapping systems.
- [ ] Develop a security model for account access, payments, logs, and any sensitive data.
- [ ] Determine whether a countywide system is technically and institutionally realistic or should begin with one city or district.

### Stage 4 — User and Assistance Workflows

- [ ] Draft a user flow for checking space rules before parking.
- [ ] Draft a voluntary reservation or short-term authorization flow where permitted.
- [ ] Define payment and cancellation rules.
- [ ] Explore nonprofit-sponsored payment assistance without exposing unnecessary personal information.
- [ ] Design alternatives for people without smartphones, bank accounts, or reliable connectivity.
- [ ] Define how users receive confirmation, expiration notices, changes, and dispute instructions.
- [ ] Ensure the system cannot imply that a payment overrides safety, accessibility, emergency, or enforcement rules.

### Stage 5 — Stakeholder Engagement

- [ ] Identify city parking, public works, planning, transportation, accessibility, finance, and information-technology staff.
- [ ] Identify county transportation, GIS, planning, and legal stakeholders.
- [ ] Consult disability-access advocates, neighborhood groups, residents, businesses, nonprofits, and parking operators.
- [ ] Engage UCSC or other academic GIS/public-policy researchers as potential reviewers.
- [ ] Prepare neutral questions about current data, authority, cost, privacy, enforcement, and operational feasibility.
- [ ] Document which agency owns each decision and avoid presenting a conceptual workflow as an existing government commitment.

### Stage 6 — Prototype

- [ ] Begin with a non-enforcement, information-only map using publicly available or agency-approved data.
- [ ] Model a small area and a limited set of space types.
- [ ] Add rule display, time windows, and a mock agreement without processing real vehicle or DMV data.
- [ ] Test accessibility, language clarity, low-bandwidth access, and non-phone alternatives.
- [ ] Conduct privacy and threat modeling before any real identity, payment, or vehicle information is introduced.
- [ ] Seek agency and legal review before field testing or connecting to operational systems.

### Stage 7 — Evaluation and Governance

- [ ] Evaluate data accuracy, user comprehension, accessibility, administrative workload, and dispute rates.
- [ ] Measure whether the system reduces confusion without increasing surveillance or unequal enforcement.
- [ ] Define data stewardship, audit rights, correction processes, retention, and deletion.
- [ ] Establish incident response and system outage procedures.
- [ ] Determine whether the project should remain an information tool, become a reservation service, or stop.
- [ ] Preserve results and unresolved issues in APO.

## Engagement Materials to Produce

1. Concept brief
2. Santa Cruz parking-system baseline
3. Data dictionary and GIS schema
4. Jurisdiction and authority map
5. Privacy and security questions
6. Stakeholder interview guide
7. Non-enforcement prototype specification
8. Accessibility and non-phone access requirements
9. Pilot evaluation plan

## Open Questions

- Who should own and maintain a countywide parking-space inventory?
- Can a space identifier be made stable when markings, construction, or regulations change?
- Which forms of temporary parking authorization are legally available?
- What information can be obtained from or connected to DMV systems, and under what authority?
- How can nonprofit assistance be offered without creating coercive disclosure or surveillance?
- How are private-property owners and residents protected from unwanted parking?
- How should the system handle accessible spaces, emergency restrictions, construction, events, and enforcement conflicts?

## Related Projects

- Community Microleasing
- Mobile Food and Music
- Santa Cruz parking and public-space regulatory research

## Current Next Action

Locate and review the specific Santa Cruz citywide permit-parking agenda materials, then define a small information-only GIS prototype that does not require DMV integration.
