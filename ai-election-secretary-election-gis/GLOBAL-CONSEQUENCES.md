# GLOBAL CONSEQUENCES — AI Election Secretary / Election GIS

## Scope

This document extends the project beyond Santa Cruz and the United States.

The goal is not to assume that all political systems use elections in the same way. The goal is to develop a research architecture capable of describing different electoral institutions accurately.

## Documented global context

UNESCO has described AI, social media, misinformation/disinformation, hate speech, surveillance, micro-targeting, censorship, internet shutdowns, and synthetic media as issues relevant to elections and information integrity. UNESCO and UNDP published a 2025 issue brief specifically examining AI, freedom of expression, and elections. [UNESCO/UNDP, 2025](https://www.unesco.org/en/articles/new-unesco-undp-issue-brief-highlights-impacts-ai-freedom-expression-and-elections)

International IDEA's 2024 report on AI for electoral management examines opportunities, challenges, and legal implications for election management bodies. [International IDEA, 2024](https://www.idea.int/publications/catalogue/artificial-intelligence-electoral-management)

International IDEA's review of the 2024 global election super-cycle examined elections across 62 countries and identified cross-country electoral-integrity challenges. [International IDEA, 2025](https://www.idea.int/publications/catalogue/review-2024-super-cycle-year-elections-trends-challenges-and-opportunities)

## The global model

The Election Secretary should have a **Political System Layer** before it creates a ballot interpretation.

Possible categories include:
- competitive multiparty democracy
- presidential democracy
- parliamentary democracy
- proportional representation
- ranked-choice / preferential voting
- referendum/initiative systems
- dominant-party systems
- competitive authoritarian systems
- single-party systems
- transitional systems
- hybrid or disputed systems

These are research classifications, not political judgments.

## Why single-party systems belong in the model

Political science research documents that elections also occur under authoritarian systems and may serve functions that differ from democratic elections. Research describes elections as potentially providing mechanisms for participation, coordination, information, legitimacy claims, elite management, or regime stability while also differing substantially in competitiveness and freedom. See:

- https://www.cambridge.org/core/journals/american-political-science-review/article/voting-in-authoritarian-elections/1C066CD75F6F070930181135B288F632
- https://www.cambridge.org/core/journals/world-politics/article/autocratic-elections/92A89B305ECE510E2556BB07BD9D4175

The project should therefore never reduce the global question to:
"Who is the opposition?"

Instead it should ask:
"What is the political function of this electoral event within this system?"

## Global consequence categories

### Information
AI can reduce the cost and time required to summarize laws, platforms, records, and election procedures.

### Verification
AI can help compare claims against primary documents, but generated answers can contain false or unsupported information. Verification must therefore be a first-class function.

### Accessibility
Translation, summarization, voice interaction, and plain-language explanations could lower barriers to participation.

### Administrative capacity
Election-management bodies may use AI for communication, document processing, cybersecurity, voter services, and other administrative tasks. International IDEA specifically studies these opportunities and risks.

### Disinformation
Generative AI can lower the cost of producing synthetic text, images, audio, and video. UNESCO identifies this as a growing information-integrity challenge.

### Microtargeting
A personalized election assistant could itself become a targeting system if political profiles are created or used for persuasion.

### Concentration of information power
If one company or model provider becomes the default civic-information gateway, access to political knowledge can become dependent on a private information intermediary.

### Cross-border effects
Political information and synthetic media can cross national borders. An election system should therefore distinguish:
- jurisdiction
- source country
- publication location
- affected population
- target population
- language
- platform

### Single-party and noncompetitive contexts
In systems with limited electoral competition, the Secretary may need to focus on:
- nomination and selection mechanisms
- intra-party processes
- local representation
- policy consultation
- formal versus practical choices
- participation
- accountability mechanisms
- public information
- constraints on opposition and dissent
- institutional checks

### Election administration
The Secretary should not assume that voters are the only users. Potential user groups include:
- voters
- election officials
- journalists
- researchers
- civil society
- observers
- accessibility advocates
- public-interest technologists

## Global design principle

The system should model elections as **institutions embedded in political systems**, not merely as ballots.

A ballot is an interface.

The political system is the underlying terrain.

The Election GIS attempts to represent that terrain without silently deciding what a person should believe about it.

## Open research questions

1. Can an AI research secretary remain neutral while choosing what to research?
2. How should source quality be represented across countries with different media environments?
3. How can the system distinguish genuine uncertainty from deliberate information suppression?
4. How should political personalization be prevented?
5. Should users be able to run multiple independent research agents and compare their source maps?
6. Can routing be made auditable?
7. Can a public-interest version operate without building a political profile?
8. What should happen when the legal meaning of an election differs from its practical political meaning?
9. How should the system handle elections where participation itself carries risk?
10. How can the system avoid becoming a political campaign machine?

## Research status

This document is a research framing, not a claim that all described effects occur equally in all countries.

The comparative literature is contested and context-dependent. Country-specific research is required before applying any category to a particular election.
