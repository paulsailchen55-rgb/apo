# Summary — AI-Mediated Influence Threat Model

This folder examines a proposed cybersecurity research problem: manipulation of the information pathway through which AI mediates between humans.

Core pathway:

adversary -> information/pathway -> AI -> output -> human -> communication/decision -> downstream humans

Four proposed channels:

1. Alteration — information, context, instructions, configuration, or output is changed.
2. Omission — relevant information is withheld or excluded.
3. Delay — timing is manipulated enough to affect a decision or action.
4. Substitution — a trusted source, model, tool, identity, or pathway is replaced.

The project connects this hypothesis to NIST AI RMF, NIST adversarial-machine-learning work, and OWASP generative-AI security guidance.

The central epistemic question is not whether the internet is "true." It is how AI systems can establish provenance, integrity, corroboration, and reliability when their information ultimately comes from human-produced sources.

The central security question is:

> Can an adversary manipulate an AI-mediated information pathway in a way that changes human communication or decision-making while making the manipulation difficult to detect?

The framework deliberately preserves alternative explanations such as ordinary model error, software defects, outages, degraded service, and ambiguous anomalies.

Evidence status:

- KNOWN — documented AI-security attack classes exist.
- CALCULATED — the four-channel model is an analytical decomposition.
- PROPOSED — AI-mediated information-pathway integrity as a threat-model layer.
- TESTED — the unified framework has not yet been experimentally validated.
- SPECULATIVE — civilization-scale coordinated "off switch" scenarios.
- UNKNOWN — which mechanisms become most important as systems become more interconnected and agentic.
