# WAYFINDER AI Local-Scribe Architecture

## Concept

WAYFINDER can use AI without making the AI itself the authority.

A small local model can act as a **scribe and interpreter** of a dated, structured local information packet. A larger remote model can be consulted for unusually complex tasks.

## Proposed hierarchy

**Local AI → local information packet → larger AI when necessary**

The durable object is the information packet, not a particular model.

## Example packet

- place
- packet version
- source URLs
- event records
- categories
- dates/times
- access conditions
- verification status
- last checked
- next review
- provenance

The model renders the packet into useful human language.

## Scribe rule

The AI should not silently upgrade uncertainty.

Example:

Source says: “coffee sometimes available.”

AI should not produce: “free coffee every Thursday.”

A scribe faithfully renders the source and preserves uncertainty.

## Source-bound safety

Prefer:

**source → structured record → verification → local packet → AI**

over:

**random Internet input → AI → asserted fact**

This does not eliminate AI error. It makes the location of an error easier to inspect and correct.

## Versioning

Packets can expire or be replaced. Rules, sources, and models should have review dates where appropriate.

## Replaceability

The packet format should be model-agnostic. A future local model, desktop model, library computer, or other AI should be able to read the same structured information.

This is a design hypothesis, not a claim that current phones can already contain a complete summary of all human knowledge.
