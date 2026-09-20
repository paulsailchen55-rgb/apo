# User-Controlled Retrieval Architecture

## Conceptual layers

1. **Open publishing layer:** accepts material from many people and organizations with a simple publishing process.
2. **Source and distribution layer:** exposes feeds, documents, structured data, or other interfaces for permitted retrieval.
3. **Indexing and retrieval agents:** collect, classify, and retrieve material according to source instructions, technical boundaries, and user requests.
4. **Personal interface:** lets each person describe what they want, set filters, save preferences, and inspect sources.
5. **Optional human-access pathways:** support direct reading or special interfaces where appropriate, without assuming that every user must be identified by location, age, or identity.

## User-directed filtering

The retrieval agent should prioritize the user's stated purpose rather than a platform's advertising goals or engagement incentives. It may ignore material that is unrelated to the request, while preserving a way to inspect source context and understand what was excluded when that matters.

Filtering should be explainable enough that users can adjust it. The system should distinguish between:

- Irrelevant to the current request.
- Not retrieved because the source was unavailable.
- Not shown because of a user-defined filter.
- Not shown because of a safety, security, or legal boundary.
- Not verified or potentially unreliable.

These categories should not be silently collapsed into one universal censorship label.

## Machine-readable publishing

The design should investigate RSS and Atom feeds, JSON and JSON-LD, schema.org data, public APIs, accessible HTML, XML sitemaps, and downloadable documents. Publishers should be able to state update times, source identity, licensing or reuse terms, and preferred retrieval methods.

A bot or AI client should identify itself where technically appropriate, follow reasonable rate limits, respect access controls and published instructions, and avoid bypassing authentication, paywalls, or other technical protections. A machine-readable interface is not automatically permission to copy everything indefinitely.

## Security boundary

The retrieval agent should not automatically execute arbitrary scripts, install software, expose private credentials, or grant a source control over the user's device. A safer architecture would separate fetching, parsing, sandboxing, storage, and presentation. The user should be able to inspect the source URL and provenance without directly opening an untrusted page.

## Families and children

The concept allows parental or household-level configuration at the interface layer. Parents or guardians could define age-appropriate retrieval settings for children without requiring every publisher to collect the child's identity, exact location, or age. This remains a difficult design and legal question and would require careful testing, accessibility work, and privacy review.

## Core principle

The publisher makes information available; the reader's interface helps the reader decide what to encounter. This division of responsibility must not be treated as a guarantee that all material is lawful, accurate, safe, or consequence-free. It is an architectural proposal for reducing unnecessary friction while preserving clear boundaries where they are genuinely needed.
