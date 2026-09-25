# AI-Mediated Influence Threat Model

**Status:** PROPOSED / RESEARCH FRAMEWORK  
**Evidence tags:** KNOWN / CALCULATED / PROPOSED / TESTED / SPECULATIVE / UNKNOWN

## 1. Purpose

This document develops the hypothesis that an increasingly important AI-security problem is not only unauthorized access to an AI system, but manipulation of the information pathway through which AI mediates between humans.

Core pathway:

**adversary -> input/context/pathway -> AI system -> AI output -> human -> communication/decision -> downstream humans**

The threat model asks whether an adversary could intentionally change what reaches the human, how it is interpreted, when it arrives, or which source/system is used, while making the manipulation difficult to distinguish from ordinary error, disagreement, model behavior, or service failure.

This is a cybersecurity research hypothesis. It does not assume that a particular attack, organization, person, or covert campaign exists.

## 2. Relationship to NIST AI RMF

NIST AI RMF 1.0 provides a useful baseline because it treats trustworthy AI as a socio-technical problem and identifies validity/reliability, safety, security/resilience, accountability/transparency, explainability/interpretablity, privacy, and fairness as relevant characteristics.

The framework here adds a narrower research lens: **AI-mediated information-pathway integrity**.

The proposed question is:

> Can the integrity, provenance, availability, timing, and identity of an AI-mediated information pathway be protected well enough that intentional manipulation can be distinguished from ordinary AI uncertainty or system failure?

This should be mapped to NIST's Govern, Map, Measure, and Manage functions rather than treated as a replacement for the AI RMF.

NIST's adversarial machine-learning taxonomy is particularly relevant because it documents attack classes including data poisoning, backdoor poisoning, prompt injection, indirect prompt injection, privacy attacks, and supply-chain attacks.

## 3. Four primary influence channels

### A. Alteration

**Definition:** Relevant information, context, instructions, configuration, or output is changed.

Examples:
- retrieved content is modified;
- a document contains instructions that change model behavior;
- system or tool context is altered;
- a summary changes the meaning of source material;
- a model configuration is changed.

**Security property:** integrity.

**Detection question:** Was the information/context actually the same information/context the trusted system intended to provide?

### B. Omission

**Definition:** Relevant information is withheld, excluded, unavailable, or never presented.

Examples:
- a source is omitted from retrieval;
- contradictory evidence is excluded;
- part of a conversation is unavailable;
- a retrieval system silently fails to return relevant material;
- a malicious or accidental filter removes information.

**Security properties:** integrity, transparency, availability.

**Detection question:** What relevant information was available elsewhere but absent from the AI-mediated pathway?

### C. Delay

**Definition:** Information, computation, communication, or access is delayed enough to change a decision or outcome.

Examples:
- service degradation;
- resource exhaustion;
- delayed retrieval;
- delayed notification;
- time-sensitive information arriving after a decision window.

**Security property:** availability, with possible downstream integrity effects.

**Detection question:** Did timing materially change what the human could know or do?

### D. Substitution

**Definition:** A trusted source, model, tool, account, identity, configuration, or communication path is replaced by another.

Examples:
- an unexpected retrieval source is used;
- a different model or configuration answers the question;
- a compromised account acts as a trusted identity;
- traffic is redirected;
- a tool or plugin is substituted.

**Security properties:** authentication, integrity, provenance, availability.

**Detection question:** Is the entity, source, model, tool, and pathway actually the intended one?

## 4. Why combinations matter

Real attacks need not fit one channel.

Examples include:
- alteration + omission;
- delay + substitution;
- omission + repetition;
- alteration + apparent authority;
- any channel + stealth/anti-forensics.

A sophisticated system can therefore resemble a **chain-reaction or Goldberg-machine-like system**: individually ordinary events can interact across many components until a later component produces the intended effect.

That analogy is useful as a systems model, but it is not evidence that a particular global system is intentionally constructed this way.

## 5. The data epistemology problem

A separate question is more fundamental:

> How do we establish what is real, authentic, representative, or trustworthy in the data from which AI systems learn or retrieve information?

The internet is not a ground-truth database. It contains primary records, secondary reporting, errors, propaganda, jokes, fabricated material, copied material, manipulated media, adversarial content, obsolete information, and mutually contradictory claims.

However, it would be too strong to conclude from that fact that training data is therefore a psychological-warfare system.

A more testable formulation is:

> AI systems inherit epistemic uncertainty from their data and can also be exposed to deliberate manipulation of training, fine-tuning, retrieval, prompts, tools, or connected resources.

NIST and OWASP already document several security classes consistent with parts of this concern, including poisoning, backdoors, prompt injection, indirect prompt injection, supply-chain risks, and connected-resource compromise.

The research problem is therefore not simply "Is the internet true?" It is:

**Which provenance, integrity, corroboration, and evaluation mechanisms allow an AI system to distinguish trustworthy information from adversarial or unreliable information?**

## 6. Hidden data and dormant triggers

The concern about information that is not obviously meaningful to a human but becomes meaningful to a machine maps onto established security research areas.

A payload does not have to be visually obvious to a human to affect a computational system. OWASP specifically notes that prompt-injection inputs can be imperceptible to humans if they are parsed by the model, and its 2025 guidance discusses indirect prompt injection through external content such as websites or files.

NIST's adversarial-ML taxonomy also includes backdoor poisoning and other attack classes involving behavior that may depend on particular conditions.

This supports investigating **conditional activation** as a threat-model concept:

**latent condition -> trigger/input/state -> unexpected model/system behavior -> downstream action**

But it is important to distinguish this from a claim that arbitrary files universally contain hidden triggers or that every anomalous behavior has a malicious cause.

## 7. Trust boundaries

The pathway should be decomposed into at least these boundaries:

1. User instructions
2. System/developer instructions
3. Retrieved external content
4. Memory/context
5. Model weights and configuration
6. Tools/plugins
7. Identity/authentication
8. Network transport
9. Device operating system
10. Output/communication channel
11. Human interpretation and decision-making

A compromise at one boundary should not automatically grant authority over every other boundary.

## 8. Stealth and anti-forensics

An adversary may attempt to:
- use legitimate credentials;
- manipulate trusted inputs;
- minimize observable artifacts;
- resemble ordinary model error;
- resemble an outage or degradation;
- change timing rather than content;
- exploit ambiguity between human error and machine behavior.

This creates an important forensic principle:

**Absence of obvious evidence does not prove that manipulation occurred, but it also does not by itself prove that manipulation was impossible.**

The practical response is independent observability: multiple trustworthy observations that can be compared after an anomalous event.

## 9. Evidence architecture

Useful evidence may include:

- authenticated timestamps;
- identity and authorization records;
- model/version/configuration identifiers;
- source and provenance metadata;
- retrieval records;
- tool invocation records;
- configuration-change records;
- integrity checks;
- availability and latency measurements;
- independent communication records;
- human approval events;
- security telemetry.

The goal is not universal surveillance. The goal is sufficient evidence to reconstruct a disputed pathway and distinguish competing explanations.

## 10. Attack vs. ordinary failure

The model must preserve alternative explanations.

Suggested classification:

1. Ordinary model error
2. Software/system defect
3. Service outage or degradation
4. Ambiguous anomaly
5. Security anomaly
6. Confirmed compromise

Movement between categories requires evidence.

This prevents the threat model from becoming unfalsifiable: an unexpected output is not automatically an attack.

## 11. Detection questions

For an important AI-mediated event, investigators should ask:

1. What was the intended objective?
2. What inputs were expected?
3. What inputs actually arrived?
4. What instructions/context were active?
5. What external sources were consulted?
6. Which model and configuration were active?
7. Which tools or plugins were invoked?
8. What output was generated?
9. What output was actually delivered?
10. Was anything altered, omitted, delayed, or substituted?
11. Can identity and provenance be authenticated?
12. Are there independent logs or observations?
13. Could ordinary model behavior explain the result?
14. Could an ordinary outage or defect explain it?
15. Is there evidence of intentional manipulation?
16. Can the finding be reproduced or independently tested?

## 12. Defensive design

Potential controls include:

- authenticated provenance;
- separation of instructions from untrusted data;
- least-privilege tool access;
- explicit human confirmation for consequential actions;
- independent information channels;
- change visibility;
- auditability;
- latency and availability monitoring;
- source corroboration;
- model/configuration attestation where practical;
- continuous adversarial testing;
- recovery and alternate pathways.

## 13. Four-channel test matrix

| Threat channel | Primary question | Main property | Example control |
|---|---|---|---|
| Alteration | Was information changed? | Integrity | Provenance and integrity checks |
| Omission | Was relevant information withheld? | Integrity / transparency | Source coverage and independent retrieval |
| Delay | Was timing manipulated? | Availability | Latency monitoring and alternate channels |
| Substitution | Was something replaced? | Authentication / provenance | Identity and source verification |

## 14. Core research hypothesis

> As AI becomes an intermediary between humans, AI security must include protection against covert manipulation of the human-AI information pathway, not merely protection against unauthorized access to the AI system itself.

This hypothesis can be tested without assuming that covert manipulation is occurring.

## 15. Research program

### Stage 1 — Taxonomy mapping
Map documented NIST and OWASP attack classes onto Alteration, Omission, Delay, and Substitution.

### Stage 2 — Evidence
Collect documented technical demonstrations, incident reports, academic research, and reproducible experiments.

### Stage 3 — Detection
Build a defender-side matrix showing what evidence would distinguish each attack class from ordinary failure.

### Stage 4 — Provenance
Define a minimum provenance record for consequential AI-mediated information.

### Stage 5 — Controlled experiments
Test whether known manipulations can change outputs while remaining difficult to detect.

### Stage 6 — False positives
Measure how often ordinary model variability, outages, data-quality problems, or user error resemble attacks.

### Stage 7 — Human-readable integrity checklist
Develop an "AI pathway integrity" checklist for non-specialists.

### Stage 8 — Framework comparison
Compare the resulting model with NIST AI RMF, NIST adversarial-ML terminology, OWASP GenAI risks, and conventional cybersecurity threat modeling.

## 16. Evidence status

**KNOWN**
- NIST identifies AI security/resilience as a core trustworthiness concern.
- NIST's adversarial-ML taxonomy documents poisoning, backdoors, prompt injection, indirect prompt injection, privacy attacks, and supply-chain risks.
- OWASP documents direct and indirect prompt injection and notes that some malicious inputs can be imperceptible to humans.

**CALCULATED**
- The four-channel Alteration/Omission/Delay/Substitution structure is an analytical decomposition proposed by this project.

**PROPOSED**
- AI-mediated information-pathway integrity as a distinct layer of threat modeling.

**TESTED**
- The unified four-channel framework has not yet been experimentally validated.

**SPECULATIVE**
- Specific claims that a hidden coordinated actor is using a global AI/internet system as a civilization-scale trigger mechanism.

**UNKNOWN**
- Which combinations of mechanisms will matter most as AI systems become more agentic, interconnected, and capable of acting through tools.

## 17. Boundary condition

This framework does not establish supernatural mechanisms, secret government programs, particular organizations, or particular individuals as causes.

The technically testable question is narrower:

> Can an adversary manipulate an AI-mediated information pathway in a way that changes human communication or decision-making while making the manipulation difficult to detect?

That question belongs within cybersecurity, AI safety/security, information integrity, provenance, and human-factors research.
