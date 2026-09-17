# Design Guardrails — The People's Relay

This is a working threat-model and ethics boundary document for an unbuilt communications concept. It is intentionally conservative about irreversible capabilities.

## 1. Primary threat categories

A communications system can be attacked or fail through more than unauthorized reading or modification.

### Confidentiality
Can an unauthorized party see information?

### Integrity
Can an unauthorized party alter information?

### Authentication
Can an unauthorized party impersonate a participant?

### Availability / disruption
Can a participant reliably communicate at all?

The fourth category is central to this concept. A message can be effectively defeated through interruption, delay, resource exhaustion, filtering, or uncertainty even if nobody reads or alters the message.

The engineering objective is not perfect availability. That is not a realistic promise. The objective is to make disruption detectable where possible, prevent silent failure where possible, and provide recovery or alternate routes where appropriate.

## 2. Human agency

The AI should assist communication, not become an autonomous political or social actor.

Preferred sequence:

**Prepare → Show → Authorize → Transmit → Report → Stop**

The user should remain the source of authorization for consequential publication or mass communication.

## 3. Capability proportionality

For every capability, ask:

1. What legitimate human purpose does this serve?
2. What could it accidentally enable?
3. What is the smallest capability that accomplishes the purpose?
4. What happens when somebody makes a mistake?
5. Can the action be stopped before it becomes consequential?
6. Can the capability be removed without destroying unrelated functions?

If a capability cannot be justified by a legitimate purpose, do not build it merely because it is technically possible.

## 4. Collective communication boundary

There is a major difference between:

- many people independently choosing to communicate a concern; and
- an autonomous system selecting targets and generating a large campaign against them.

The Relay should support individual agency and, where appropriate, transparent aggregation. It should not become an autonomous influence cannon.

Examples of capabilities to avoid:

- autonomous target discovery
- autonomous harassment
- autonomous retaliation
- autonomous escalation
- endless automated retries against an unwilling recipient
- hidden mass-mailing behavior
- impersonation
- covert coordination intended to evade accountability

## 5. Delayed-release and dead-man mechanisms

A delayed release or dead-man switch can transform an ordinary communications system into a persistence mechanism with consequences that occur after the initiating person is unavailable.

For this concept, dead-man publication and hidden delayed-release mechanisms are explicit non-goals.

The philosophical idea of people leaving messages, memories, inventions, or other effects after death can be preserved without implementing an automated death-triggered publication system.

## 6. No universal god-mode

Avoid a secret administrative mechanism that allows one operator to:

- read everybody's messages;
- impersonate everybody;
- remotely operate devices;
- publish as users;
- silently disable all users;
- or reconstruct the complete communications graph.

If emergency controls ever become necessary, their authority should be narrow, documented, auditable, and separated from message confidentiality and user identity wherever practical.

## 7. Compartmentalization

A resilient architecture should assume that some component will eventually be compromised.

Design goal:

> **Breaking one piece should not reveal the whole picture.**

Possible techniques include:

- least privilege
- separate services
- multiple relay operators
- hardware-backed keys
- minimal metadata
- local processing
- explicit external-AI authorization
- independent security review
- open source
- reproducible builds where practical
- documented dependencies
- rapid patching

## 8. Privacy is not anonymity

Encryption, local processing, or a privacy gateway can reduce exposure. They cannot honestly guarantee that nobody can observe, retain, correlate, or block communications.

The project should state exactly what it protects and what remains outside its control.

## 9. Ephemeral context

A possible privacy workflow is:

**Extract task → minimize context → transform/redact where appropriate → obtain authorized external assistance → discard unnecessary external context → integrate result locally**

This is a design objective, not a promise about what a third-party provider may retain. Provider policies and technical behavior must be verified independently.

## 10. Delivery truth

The system should not call a message “delivered” merely because a local process accepted it.

Possible states:

**Prepared → Authorized → Accepted by relay → Queued → Transmitted → Recipient acknowledged**

The exact state machine must be defined per channel because email, SMS, physical mail, and other transports provide different guarantees.

## 11. Failure and recovery

The design should prefer reversible failures over irreversible ones.

A useful failure message is:

> **Transmission interrupted. Recipient confirmation is unavailable.**

not:

> **Sent.**

when the system cannot substantiate that claim.

Recovery may include retrying under user control, selecting another authorized transport, saving the message locally, or asking the user what to do next.

## 12. Economic incentives

The project should examine how financing changes communication behavior.

Money is not itself the enemy. Infrastructure requires resources. The relevant questions are:

- What is the legitimate service being paid for?
- What information is necessary to provide it?
- What additional data or attention is extracted?
- Does the revenue model reward surveillance, addiction, manipulation, or unnecessary friction?
- Can a sustainable model preserve user agency?

A working design principle is:

> **Do not make the people using the communication system into an unnecessarily extracted resource.**

## 13. Learning from previous technology

Early public-computing experience is retained as a warning: systems deployed to real users can behave differently from the assumptions made by their designers. Unexpected content, workloads, interactions, and misuse can expose failure modes.

Therefore:

> **Design for surprise.**

Test realistic misuse cases, resource exhaustion, malformed input, dependency failure, network interruption, accidental user actions, and adversarial behavior before deployment.

## 14. Responsible development gate

Before adding a consequential feature:

**Purpose → Threat model → Minimal capability → Prototype → Adversarial testing → Human review → Document limitations → Release narrowly → Observe → Revise**

The process should permit saying “not yet” or “do not build this.”

## 15. Project boundary

The Relay is not intended to guarantee that institutions cannot interfere with it. It is intended to reduce unnecessary centralized power and preserve individual agency.

The target is not:

> **A machine nobody can stop.**

The target is closer to:

> **A communications utility that does not secretly acquire the power to control the people using it.**

## Working maxim

> **Radical about human agency. Conservative about irreversible power.**

> **Dream weird. Verify everything.**
