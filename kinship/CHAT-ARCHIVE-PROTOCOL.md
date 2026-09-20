# KINSHIP Chat Archive Protocol

KINSHIP is developed through conversation as well as formal engineering work. Conversation contains design provenance that can be lost if only final conclusions are retained.

## Working rule

At the end of a significant KINSHIP conversation, the user may say:

**“Archive this KINSHIP chat.”**

The assistant should then:

1. Identify reusable KINSHIP material from that conversation.
2. Preserve important original wording when provenance matters.
3. Separate canonical conclusions from hypotheses and unresolved ideas.
4. Update the appropriate KINSHIP document(s).
5. Add a dated conversation/archive record when the conversation contains substantial design history.
6. Update CHANGELOG.md when the repository meaningfully changes.
7. Never silently overwrite earlier provenance.
8. Never modify APO root documentation unless explicitly requested.

## Two-layer record

KINSHIP should maintain both:

- **conversation/provenance records**, preserving how ideas emerged;
- **canonical engineering documents**, progressively refining the ideas into requirements, models, tests, and evidence.

The canonical document may become cleaner than the conversation. The provenance record should not be rewritten merely to make history cleaner.

## Important limitation

The assistant cannot assume that an old conversation will remain available indefinitely. If a conversation contains important KINSHIP material, archive it while it is available rather than relying on future recall.
