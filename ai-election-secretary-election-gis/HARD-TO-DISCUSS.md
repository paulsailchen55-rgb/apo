# HARD TO DISCUSS — AI Election Secretary / Election GIS

This file deliberately records risks and questions that should not be hidden merely because they make the project harder to build or discuss.

## 1. A political research assistant can become a political influence system

A system that discovers, summarizes, compares, maps, and routes political information can influence decisions even if it never explicitly says "vote for X."

Risk:
- framing effects
- source selection effects
- omission
- ordering effects
- visual symbolism
- repeated exposure
- personalized issue emphasis
- automated "helpfulness" that quietly becomes persuasion

Design requirement:
The system should separate documented facts, attributed claims, analysis, uncertainty, and user-authored conclusions.

## 2. Personalization can become political profiling

A secretary that knows a person's interests, history, location, reading habits, and previous political questions could construct an unusually detailed political profile.

Risk:
- political microtargeting
- inferred political preferences
- political persuasion
- discrimination
- surveillance
- data brokerage
- permanent records of sensitive civic behavior

Design requirement:
Do not infer or store voting preferences merely because the system can.

## 3. AI routing can become hidden gatekeeping

If a router decides which AI receives a political question, the router effectively controls the research pipeline.

Risk:
- one provider becomes the default political information gatekeeper
- proprietary ranking affects what evidence is seen
- model differences create hidden conclusions
- tool availability determines research depth

Design requirement:
Record routing decisions and allow human inspection and, where practical, alternative-source research.

## 4. Citation laundering

An AI can produce a chain that looks well sourced while the underlying source does not actually support the claim.

Design requirement:
For important claims, preserve:
SOURCE -> EXCERPT/LOCATION -> CLAIM -> INTERPRETATION.

## 5. Adversarial research can become false balance

"Research both sides" does not mean every claim has equal evidentiary support.

Design requirement:
Represent disagreement accurately without manufacturing equivalence. Distinguish:
- documented fact
- credible disagreement
- unsupported assertion
- unresolved question
- disproven claim

## 6. The relational map can persuade without words

A map can imply importance through size, color, proximity, motion, fire, growth, or destruction.

Design requirement:
Visual encoding should describe evidence relationships, uncertainty, conflict, or jurisdiction—not political goodness/badness.

## 7. Automated publishing can turn research into campaign infrastructure

The same system that researches a measure could automatically publish persuasive material to websites and social networks.

Risk:
- political spam
- synthetic grassroots activity
- automated campaign messaging
- mass persuasion
- impersonation
- election-period information flooding

Design requirement:
Separate research mode from publication mode and require explicit human review before political publication.

## 8. Elections outside liberal democracies are not interchangeable

A U.S.-style ballot model may fail to describe elections in dominant-party, authoritarian, or single-party systems.

Risk:
The system could misclassify participation, opposition, legitimacy, or the purpose of an election.

Design requirement:
Represent the political system itself as a layer before interpreting the meaning of the ballot.

## 9. Single-party systems still require research, but not the same research

A "candidate dossier" in a single-party system may need to examine:
- nomination mechanisms
- intra-party competition
- local versus national selection
- turnout requirements or incentives
- formal versus practical choice
- policy consultation
- public participation
- dissent constraints
- institutional accountability

The system should not assume that the absence of multiple parties means the absence of meaningful political processes, nor should it assume the reverse.

## 10. AI can become an authority by accident

The phrase "the AI researched it" can itself become a substitute for evidence.

Design requirement:

> AI is a research instrument, not the authority.

The system should always preserve a route back to primary or otherwise identified sources.

## 11. The global consequence

A widely deployed Election Secretary could potentially change:
- how quickly citizens can understand complicated ballots
- how much research ordinary people can perform
- how journalists investigate candidates
- how civil society monitors elections
- how campaigns respond to claims
- how election administrators communicate
- how misinformation is challenged
- how political information is distributed

It could also amplify manipulation at the same scale.

Therefore the project should be treated as civic infrastructure with a threat model, not merely as a productivity application.

## 12. The deepest unresolved question

If an AI can assemble a more complete political picture than an individual human can reasonably assemble alone:

**Who controls the map?**

Possible answers should be researched rather than assumed:
- the user
- the public
- election administrators
- independent civil society
- multiple competing providers
- open-source communities
- journalists
- some combination

This question belongs at the center of the project.
