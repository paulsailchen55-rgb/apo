# Conversational Letter Secretary

## Status

**PROPOSED / RESEARCH AND PROTOTYPE CONCEPT**

This project explores an AI-assisted system for discussing, drafting, reviewing, addressing, authenticating, and sending letters or emails through a user-authorized communication account.

The initial experiment should avoid connecting to the user's primary Gmail account. Outlook may be evaluated as a separate provider, subject to account availability, permissions, and supported authentication methods.

## Core Idea

The user and an AI assistant discuss the purpose and content of a letter. The system helps produce a draft, identifies or confirms the intended recipient, displays the exact final message, and requires an explicit user authorization step before sending.

The user should remain in control of the final send action.

## Intended Workflow

1. Discuss the purpose and audience.
2. Draft and revise the letter.
3. Verify the recipient, address, subject, and attachments.
4. Present the complete final message.
5. Require explicit approval.
6. Authenticate the user through a provider-supported passkey, device PIN, biometric confirmation, or equivalent mechanism.
7. Send through the authorized email provider.
8. Record the send result separately from any claim of delivery.

## Initial Boundary

The first prototype should be text email only, with no automatic sending, no access to the primary Gmail account, and no storage of passwords, passkeys, biometric data, or private authentication secrets in the repository.

## Evidence Labels

- **KNOWN:** Email providers and authentication systems expose documented capabilities that must be verified for the selected account.
- **PROPOSED:** Conversational drafting plus explicit approval and authenticated sending.
- **UNKNOWN:** Exact ChatGPT-to-Outlook permissions, available send actions, account requirements, and whether a fresh authentication prompt can be enforced for every message.
- **TESTED:** No end-to-end sending test has been completed in this project.

## Related Concepts

- One-Number AI Secretary
- Open/free web linking ecosystem
- Civic communication and two-minute speech projects

## Principle

AI may prepare and organize communication, but the human sender must retain meaningful control over the recipient, content, authorization, and final transmission.
