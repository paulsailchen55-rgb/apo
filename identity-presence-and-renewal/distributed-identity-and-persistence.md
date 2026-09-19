# Identity, Persistence, and the Distributed Technology Landscape

## Purpose

This document extends the **Identity, Presence, and Renewal** project into the larger family of technologies now being used to represent identity, credentials, transactions, records, ownership, and relationships across distributed networks.

The purpose is not to decide that blockchain, decentralized identity, or any other technology is inherently good or bad. The purpose is to understand what each technology makes persistent, what it makes discoverable, what it makes verifiable, what can be corrected or retired, and who retains control over those processes.

A central question is:

> What kind of persistence should each kind of identity information have?

A second question follows:

> If an identity system is designed to remember almost everything, how does a person retain the ability to correct, renew, retire, or appropriately disappear from parts of that system?

These questions are part of the identity project because identity is increasingly being connected to money, credentials, records, searchability, and automated decision systems.

## The larger technology family

The project should investigate the related technologies together rather than treating "blockchain" as the entire field.

The working technology map includes:

- Distributed Ledger Technology (DLT)
- blockchain systems
- peer-to-peer networks
- decentralized identifiers (DIDs)
- verifiable credentials (VCs)
- public-key and cryptographic identity
- decentralized and content-addressed storage
- IPFS and related content-addressed systems
- distributed databases
- distributed hash tables
- zero-knowledge proofs
- smart contracts
- token systems
- stablecoins and other digital-money systems
- central-bank digital-currency architectures where DLT is considered
- decentralized autonomous organizations
- decentralized or persistent archival systems
- revocation and credential-status mechanisms
- privacy-enhancing technologies
- other systems that separate identity, proof, storage, and authority

These technologies overlap, but they are not interchangeable. A decentralized identifier does not require a blockchain. A verifiable credential does not require a blockchain. Distributed storage is not the same thing as a distributed ledger. A persistent record is not necessarily a public record, and a public record is not necessarily permanent.

## Why blockchain matters to identity

Blockchain introduces a particularly important identity question because it is designed to maintain a shared historical record across multiple participants.

The National Institute of Standards and Technology describes blockchain as a shared, tamper-evident and tamper-resistant digital ledger in which transactions are grouped into cryptographically linked blocks and copies are maintained across nodes. NIST also cautions that "immutable" is often used too broadly: blockchains are not absolutely immutable in every circumstance.

That distinction matters for identity.

Deleting a local copy, deleting a wallet, losing a private key, shutting down a server, or closing an account does not necessarily erase historical information from a distributed ledger.

Bitcoin provides a useful example. Full nodes validate the blockchain, while archival nodes may retain the entire historical chain; Bitcoin also supports pruned nodes that discard older blocks locally. Local deletion therefore has to be distinguished from alteration of the shared historical record.

The project should therefore avoid the simplistic statement "blockchain means forever." The more precise research question is:

> Under what technical, social, economic, and legal conditions can a record remain available, reconstructable, verifiable, interpretable, or recognized over time?

## The deletion and erasure problem

The European Data Protection Board's 2025 Guidelines 02/2025 on processing of personal data through blockchain technologies are especially relevant to this project. The guidelines emphasize that blockchain's distributed nature creates particular data-protection challenges and that data-protection principles such as storage limitation, data minimization, rectification, and erasure can be difficult to reconcile with some blockchain designs.

The EDPB states that, as a general rule, storing personal data on a blockchain should be avoided where doing so conflicts with applicable data-protection principles. It also notes that once a transaction is recorded, it generally cannot be individually altered or removed without detection, and that blockchains have limited ability to step back or delete individual transactions. Where personal data is stored directly on-chain, actual deletion may be technically impracticable.

This makes the EDPB material an important part of the project's evidence base, not because it settles the question for every jurisdiction or every architecture, but because it documents a major institutional recognition of the tension between distributed persistence and rights involving personal data.

The project should continue to distinguish:

- deletion from one device;
- deletion from one service;
- deletion from a local database;
- revocation of a credential;
- invalidation of a key;
- removal of an off-chain record;
- disappearance from search results;
- cryptographic unlinking;
- alteration of a distributed record;
- destruction of every meaningful copy;
- and legal recognition that information should no longer be used.

These are different events.

## Persistence is not one property

"Permanent" should be treated as a family of properties rather than a single technical characteristic.

A record can have:

1. persistence — copies continue to exist;
2. availability — people can still retrieve it;
3. integrity — there is evidence that it has not been altered;
4. interpretability — future systems can understand what it means;
5. verifiability — its authenticity or provenance can still be checked;
6. social recognition — institutions continue to treat it as authoritative;
7. legal relevance — a legal system continues to recognize or regulate it.

Any of these can fail independently.

This is especially important when considering the user's speculation that physical storage media could someday become archaeological evidence. It is possible in principle for physical remnants of digital systems to survive beyond their original institutions, but this is not guaranteed. Survival of bytes does not automatically preserve the software, keys, protocols, context, or social meaning required to reconstruct what those bytes meant.

## The identity architecture to investigate

A major direction emerging from this project is an architecture that separates identity from permanent publication of personal information.

The working architecture is:

**person-controlled identity + credential proofs + revocable or status-aware credentials + recoverable references + externally stored personal data + selective disclosure**

The idea is to preserve the ability to prove appropriate facts without requiring the underlying personal information to become a permanent public record.

This is compatible with the direction of decentralized identity standards. The W3C Decentralized Identifiers specification describes DIDs as identifiers controlled by their subject and decoupled from centralized registries or identity providers. It explicitly permits a person or entity to have multiple DIDs for different contexts or personas and does not require DIDs to use blockchains.

The W3C Verifiable Credentials model similarly provides a way to express machine-verifiable claims while separating the credential from the entire body of personal information that may have been used to establish the claim. Credential status, expiration, refresh, and revocation are therefore important parts of the identity architecture.

The project should investigate whether this kind of separation allows identity to be persistent without making every piece of identity information permanent.

## A possible design rule

One emerging principle is:

> Do not place information into a persistence system whose lifecycle exceeds the legitimate lifecycle of the information itself.

A related principle is:

> Do not make identity persistence depend upon permanent retention of personal data.

And another is:

> Separate proof of a fact from permanent publication of the information used to establish that fact.

These are research and design principles, not established technical laws.

## Identity information should have different lifecycles

The project should not ask whether "identity" should be permanent. It should ask how long each category of identity information should persist.

A preliminary matrix is:

| Information | Possible lifecycle | Discoverability | Correction / retirement question |
|---|---|---|---|
| Public name and profile | Long-term | Often discoverable | Can the person update or retire it? |
| Current contact method | Current | Limited | Should become replaceable or erasable |
| Public project history | Long-term | Often discoverable | Which portions should remain archival? |
| Credential | Defined validity | Verifiable when presented | Can it expire or be revoked? |
| Private personal data | Limited | Not public by default | Must remain correctable and erasable where appropriate |
| Temporary account | Short/contextual | Context-dependent | Should it disappear when its purpose ends? |
| Financial transaction record | Legally and institutionally determined | Context-dependent | What retention rules apply? |
| Cryptographic proof or hash | Potentially long-lived | Context-dependent | Can the associated information be changed or unlinked? |
| Historical archive | Potentially very long | Deliberate | What is the archival purpose and authority? |

This matrix is deliberately provisional.

## Identity, money, credentials, records, searchability, and privacy

A major convergence point for the project is:

**identity + money + credentials + persistent records + searchability + privacy**

These systems are increasingly capable of interacting.

If they become tightly coupled, the question "Who am I?" becomes partly a question about:

- what records about me exist;
- which records can be found;
- which records can be linked together;
- which records can be used to make decisions about me;
- which records I can correct;
- which records I can remove;
- which identities I can retire;
- which identities I can keep separate;
- and who has authority to perform those operations.

This creates an important distinction between a coherent identity and a universally trackable identity.

The project is interested in a person being able to demonstrate that multiple public representations belong to the same person when appropriate, while still allowing particular activities to remain private, anonymous, or pseudonymous when there is a legitimate reason for doing so.

A library-card analogy is useful here: a person can be recognized as an authorized participant in an institution without every individual act of inquiry necessarily becoming a public biography of that person.

## Presence versus continuous surveillance

The natural-world observation behind this project is deliberately simple.

A bird can appear, sing, and then leave. A butterfly or dragonfly may be present for a short period. A squirrel may appear and disappear. An oceanfront or river can remain present over long periods while continually changing.

These forms of presence do not require continuous identification of every movement.

This raises a design question for digital systems:

> Can a person be present and discoverable without being continuously observable?

The project therefore distinguishes presence from surveillance.

A person may need a durable way to be found, identified, contacted, or held accountable in appropriate circumstances without requiring every moment, movement, inquiry, transaction, or association to become a permanent record.

The concern about surveillance is therefore treated as one property or aspect of the identity problem, not as the entire definition of the project.

## Presence, search, and the loss of simplicity

The original practical experiment began with a simple problem: how can a person make themselves findable on the Internet?

That simple question has expanded into a complex technical ecosystem involving search engines, profile pages, repositories, professional networks, identifiers, credentials, cryptographic keys, databases, distributed ledgers, decentralized storage, and automated systems.

There is a tension here.

In physical life, presence can be extremely simple. A person is somewhere. A bird is there. A river is there. A shoreline is there. Someone can encounter them without requiring a global identity graph.

Digital systems can instead make presence persistent, searchable, linkable, measurable, and potentially actionable at enormous scale.

The project should therefore investigate whether technological complexity is solving the identity problem or creating additional identity problems that then require further technologies to manage.

## Automation, feedback loops, and intelligent systems

Another research direction emerged from considering credit systems and automated correction or removal processes.

People already interact with systems that maintain records, evaluate information, process disputes, and accept requests for correction or removal. The user is interested in whether increasingly autonomous or intelligent systems could eventually automate some of these feedback loops.

A possible trajectory is:

**record → dispute/correction request → automated processing → updated status → further automated interpretation**

The user has also raised the possibility that mechanisms invented by people to manage records could eventually become increasingly intelligent, autonomous, and redundant of earlier human administrative processes.

This is not presented here as a verified prediction. It is a research question about the application of increasingly autonomous intelligence to identity, credit, records management, credentialing, and human institutions.

The project should investigate both the potential usefulness and the risks of such automation, especially when an automated system is making decisions about whether an identity record remains active, correct, relevant, visible, or retired.

## Human lifecycle and system lifecycle

The identity project can also be compared with equipment lifecycle.

Continuous ownership does not require continuous operation.

A device can be:

- active;
- shut down;
- inspected;
- cleaned;
- repaired;
- restored;
- placed into storage;
- repurposed;
- archived;
- retired;
- or disposed of.

Digital identities may require similar lifecycle states.

This supports a broader design question:

> Why should a digital identity be expected to remain continuously active simply because the person remains alive?

The project is interested in identity systems that permit periods of activity, rest, maintenance, correction, renewal, separation, and retirement.

## Sabbath, automation, and the limits of this claim

A religious/philosophical thread in the user's reasoning connects Sabbath with the idea that human systems can include deliberate periods of rest rather than continuous operation.

The user has also wondered whether the understanding associated with a Sabbath day could eventually be expressed in the design of increasingly intelligent or autonomous systems: not necessarily as a religious requirement imposed on technology, but as an example of a human principle in which continuous activity is deliberately interrupted by a recurring period of rest.

This is not a verified claim about the future of artificial intelligence, nor is it a claim that autonomous systems should literally observe a religious Sabbath.

It is a conceptual research question:

> Can intelligent systems be designed with meaningful cycles of operation, rest, maintenance, reflection, correction, and renewal rather than assuming that maximum continuous activity is always the desired state?

The religious provenance should remain distinguishable from the technical hypothesis.

## Global scope

The identity problem is not confined to one country.

The Internet crosses national borders. Distributed systems can operate across jurisdictions. A credential issued in one place may be presented somewhere else. A public blockchain can have participants in many countries. Privacy and data-protection laws differ. The same identity architecture can therefore encounter conflicting expectations about permanence, deletion, anonymity, accountability, and public access.

The European Data Protection Board material is one important example of a jurisdictional and institutional response to these tensions. It should be studied alongside other legal and technical approaches rather than treated as a universal rule.

## Research boundaries

This document contains several different kinds of material and they should remain distinguishable:

- externally documented technical facts;
- standards and institutional guidance;
- personal observations;
- design principles;
- philosophical questions;
- religious provenance;
- hypotheses about future automation;
- speculative long-term scenarios.

The project should not turn a personal observation into a technical fact, or a religious premise into a universal engineering requirement.

## Working questions

1. What kind of persistence should each kind of identity information have?
2. What should be persistent, and what should be erasable?
3. What is the difference between identity, presence, discoverability, authentication, accountability, and surveillance?
4. Can a person have a persistent identity without creating a permanent public dossier?
5. Can credentials be verifiable without permanently exposing the underlying personal information?
6. Can a person prove that multiple public identities belong to them without making every activity linkable?
7. What role should DIDs, verifiable credentials, public-key cryptography, and zero-knowledge proofs play?
8. Which uses of blockchain actually require a ledger, and which are better served by other architectures?
9. What should be stored on-chain, if anything?
10. What should remain off-chain?
11. How should revocation, expiration, correction, and retirement work?
12. What happens when a system designed for persistence outlives the legitimate purpose of the information?
13. How should identity systems respond to privacy and erasure requirements?
14. How can searchability support human connection without becoming continuous surveillance?
15. Can digital systems support meaningful periods of rest and non-operation?
16. What happens when autonomous systems begin managing their own identity and record-maintenance processes?
17. How should human beings retain authority over automated identity systems?
18. What should happen when a person dies, changes identity, changes profession, changes affiliation, or simply wants an old identity to end?
19. What information should be preserved for legitimate historical purposes?
20. What information should be allowed to disappear?

## Provisional core principle

The strongest formulation emerging so far is:

> Identity should be persistent enough to support presence, recognition, accountability, continuity, and human connection, but not so persistent that the persistence itself becomes a substitute for the person.

A related architectural principle is:

> Preserve the ability to prove what needs to be proved without permanently publishing everything that was used to prove it.

These principles remain open for testing against real standards, technologies, laws, and lived experience.
