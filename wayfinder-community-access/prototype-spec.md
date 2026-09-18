# WAYFINDER v0.1 Prototype Specification

## Goal

Build the smallest working local prototype before attempting national or global coverage.

## User flow

1. Open WAYFINDER.
2. Choose or enter a city/area.
3. Select today or another date.
4. Browse the ten categories.
5. Open a listing.
6. See source, time, location, access information, and verification status.
7. Report whether the information matched.

## Prototype architecture

**Public/static layer**
- simple webpage
- black-and-white Wayfinder visual identity
- structured public event data

**Data layer**
- CSV/JSON during initial testing
- eventual interoperable ICS generation

**Verification layer**
- simple feedback endpoint or stub
- future anonymous/pseudonymous backend
- anti-abuse and rate-limit requirements documented before public deployment

**AI layer**
- research/extraction assistance
- source-aware summarization
- no silent invention
- no organization ranking

## First test

One Santa Cruz area, one day, ten categories.

Measure:
- number of useful listings
- time to discover
- time to verify
- percentage machine-accessible
- percentage requiring human confirmation
- stale/conflicting information
- usefulness to a person trying to decide what to do today

## Explicit non-goals

- worldwide city enumeration
- popularity ranking
- organization reputation scoring
- territorial symbol system
- replacement of all existing community directories
- dependence on one AI provider
