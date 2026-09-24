# AI Election Secretary / Election GIS

Status: PROPOSED / RESEARCH ARCHIVE

This folder preserves the evolving concept developed in conversation on 2026-09-24.

## Core concept

An **AI Election Secretary** is a human-directed research and routing system for elections and civic decisions.

It does not decide how a person should vote. It helps a person discover what they are being asked to decide, research the relevant evidence, identify uncertainty and disagreement, map relationships, route specialized tasks to appropriate AI/tools, and preserve the resulting work.

The system is paired with an **Election GIS / Civic Decision Map**.

The map treats jurisdictions, offices, candidates, measures, policies, institutions, evidence, affected populations, and relationships as layers over geographic and institutional terrain.

## Core workflow

1. DISCOVERY — What am I actually being asked to decide?
2. BRIEF — What is this decision? Use a short executive brief with expandable detail rather than an artificial one-page limit.
3. EVIDENCE DOSSIER — What do we actually know? Preserve claims, sources, dates, source types, calculations, contradictions, and unknowns.
4. ADVERSARIAL RESEARCH — What is the strongest documented argument or evidence on the other side? What could make the initial interpretation wrong?
5. SOURCE COMPARISON — Compare primary sources, independent analysis, journalism, research, and competing claims without collapsing disagreement into a single score.
6. RELATIONAL MAP — Connect people, offices, laws, policies, organizations, funding, statements, geography, and effects.
7. DECISION TREE — Organize the actual ballot into human decisions. The final decision remains the user's.
8. ARCHIVE / PROVENANCE — Preserve the research path so later conclusions can be traced back to evidence.

## Three concentric circles

### Circle 1 — MY BALLOT
Things the person can actually vote on in the current election.

### Circle 2 — MY GOVERNMENT
Officials, institutions, and policies governing the person's community even when the official is not up for election in the current cycle.

### Circle 3 — MY ENVIRONMENT
State, federal, regional, neighboring-jurisdiction, regulatory, economic, environmental, and other decisions that may affect the person's community even when the person cannot directly vote on them.

A fundamental design distinction is:

**VOTABLE BY ME** != **RELEVANT TO ME**

## Candidate dossier

A candidate is represented as a research object rather than merely a biography.

Possible layers:
- office and jurisdiction
- qualifications and professional history
- stated priorities
- documented votes and actions
- legislation
- administrative record
- appointments
- campaign finance
- endorsements
- opposition
- organizations
- public statements
- corrections or disputes
- conflicts of interest
- policy positions
- affected populations
- geographic effects
- unknowns

Optional layers can be switched on/off.

## Candidate GIS / relational map

Two or more candidates can be placed side-by-side on the same geographic/institutional map.

The visualization should not rank or score candidates. It should expose relationships and evidence.

Possible visual states:
- documented relationship
- policy jurisdiction
- evidence-backed connection
- unresolved question
- conflicting evidence
- high-conflict research zone

A visual metaphor such as terrain, growth, erosion, or fire may be used, but must represent the state of the research rather than declare a political winner or loser.

## Measures

Measures require a distinct research model.

For each measure:
- exact legal text
- existing law
- proposed change
- authority
- implementation mechanism
- fiscal effects
- affected populations
- geographic effects
- time horizon
- proponents and opponents
- official analysis
- independent analysis
- strongest arguments on both sides
- uncertainty
- interaction with other laws/measures

Statewide measures should be researched for their possible effects on local communities even when local voters are not choosing a local version of the policy.

## AI routing

The Secretary is the conductor, not necessarily the only model.

Possible routing:
- webpage -> extraction/research
- long PDF -> document analysis
- legislative record -> legislative/database research
- campaign finance -> finance database
- scientific claim -> scientific literature
- legal question -> primary legal sources
- candidate comparison -> evidence synthesis
- relationship mapping -> graph/visualization engine
- publishing -> document/GitHub/web tools

The router should explain why a tool/model was selected and preserve provenance.

## Global scope

The concept is intentionally not limited to U.S. two-party democratic elections.

It should be capable of representing:
- multiparty democracies
- proportional systems
- ranked-choice systems
- presidential and parliamentary systems
- referendums and initiatives
- local elections
- dominant-party systems
- competitive authoritarian systems
- single-party or effectively noncompetitive electoral systems
- elections where the main political function is not ordinary competitive transfer of power

The system must not assume that an election means the same thing everywhere.

## Non-democratic / single-party contexts

Research must distinguish:
- election event
- electoral institution
- degree of competition
- candidate/party choice
- freedom of information and association
- ballot secrecy and coercion
- administrative independence
- legitimacy claims
- opportunities for participation or dissent
- consequences of participation/nonparticipation

Comparative political research documents that elections can exist under authoritarian rule and can have different functions from elections in democratic systems. The system should represent those differences rather than applying a U.S.-style ballot model universally.

## Design principle

> Preserve the person's ability to understand the decision before asking the person to make the decision.

This project is an archive of possibilities, not an electoral authority.
