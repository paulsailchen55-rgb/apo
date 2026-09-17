# Android Device Observer Archive — 2026-09

This folder preserves a working conversation and research record about understanding and reducing unnecessary Android/Motorola/carrier software activity on a Motorola phone.

## Archive status

This is an **archive/reference package, not a finished product**. The material records observations, hypotheses, decisions, and possible future research. It intentionally does not convert suspicions into established facts.

The surrounding repository, `apo`, is treated as an **Archive of Possibilities**. This folder follows the principle: **preserve the possibility before deciding what it is.**

## Contents

- `phone-cleanup-and-component-review.md` — working record of the component-by-component cleanup and investigation.
- `observer-project-notes.md` — the emerging concept for a local-first device observer/logger and a disciplined method for separating observations from accusations.
- `source-and-scope.md` — provenance, scope, and unresolved questions.

## Working decision language

- **LEAVE ALONE** — currently treated as core infrastructure or not sufficiently understood to justify changing it.
- **DISABLE** — considered optional and appropriate to disable when the stated use case does not need it.
- **RESTRICT** — reduce background freedom without removing the component.
- **INVESTIGATE** — potentially relevant, but evidence is insufficient for a safe conclusion.
- **OBSERVE** — leave functioning while looking for measurable relationships or effects.

These labels are working decisions, not claims about intent or wrongdoing.
