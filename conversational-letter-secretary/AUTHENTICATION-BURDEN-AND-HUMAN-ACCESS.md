# Authentication Burden and Human Access

## Status

**PROPOSED / OBSERVATION FOR RESEARCH**

## Core Observation

A communication system can become difficult for ordinary people to use when authentication, account verification, provider restrictions, anti-abuse checks, and repeated authorization steps accumulate before a basic action—such as sending an email—can be completed.

The project should investigate whether security controls are creating an unreasonable human-access burden, especially for people with limited time, money, reliable devices, phone access, technical knowledge, or available recovery methods.

The objective is not to remove meaningful security. It is to reduce unnecessary friction while preserving clear user authorization and safeguards against abuse.

## AI and Automated Abuse Hypothesis

**SPECULATIVE / TO BE INVESTIGATED:** Increasingly capable AI agents, bots, spam systems, credential abuse, and other automated activity may be contributing to providers introducing stricter identity, account, and sending controls. The project must not assume that every verification requirement is caused by AI; each provider's stated rationale and actual technical requirement should be documented separately.

## Design Question

How can a system distinguish a legitimate human-approved communication from harmful automation without making normal human communication practically inaccessible?

## Proposed Design Principles

1. **One understandable authorization path:** Explain why a verification step is required and avoid redundant loops where possible.
2. **Human-scale interaction:** Design for people using ordinary phones, limited data, low income, disabilities, or inconsistent access to devices and phone numbers.
3. **Security proportionality:** Match the level of verification to the risk of the action rather than applying the same burden to every message.
4. **Separate identity from intent:** Verifying that a person controls an account does not by itself verify the recipient, message content, or purpose.
5. **No hidden escalation:** Tell the user when an additional verification step is required, who requires it, and whether it can be avoided or replaced with another supported method.
6. **Graceful fallback:** Provide legitimate recovery and alternative authentication paths without asking the user to surrender passwords, biometric data, or private keys to the project.
7. **Human confirmation without endless repetition:** Preserve a clear final approval step while investigating whether trusted device authentication, passkeys, or short-lived authorization can reduce repeated prompts.
8. **Accessibility as a security requirement:** Treat excessive complexity, unavailable phone verification, and inaccessible recovery methods as potential barriers to safe communication.

## Questions to Document During Testing

- How many distinct steps are required before a new user can send one plain-text message?
- Which steps are required by the email provider, the operating system, the integration, or the application itself?
- Which steps repeat for every message, every session, or only when risk signals change?
- What happens when the user has no available phone number, loses a device, or cannot use a particular biometric method?
- Can the user understand what is being verified and why?
- Can the user cancel safely before transmission?
- Does the system provide a meaningful distinction between account authentication, recipient verification, anti-spam screening, and delivery status?

## Evidence Labels

- **KNOWN:** Authentication and anti-abuse controls can affect access to communication services; exact causes and requirements must be verified provider by provider.
- **PROPOSED:** A human-centered communication system that minimizes unnecessary authentication burden while retaining meaningful safeguards.
- **SPECULATIVE:** AI and bot abuse may be one factor behind tightening controls.
- **UNKNOWN:** The actual number, purpose, and necessity of verification steps for each candidate provider and integration.
- **TESTED:** No comparative human-burden test has yet been completed.

## Boundary

This document does not advocate bypassing legitimate security controls. It proposes documenting their effects, identifying redundant burdens, and designing safer, clearer, and more accessible authorization workflows.
