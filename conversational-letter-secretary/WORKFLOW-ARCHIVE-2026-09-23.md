# Workflow Archive — 2026-09-23

## Archival Candidate

A proposed conversational letter-sending assistant that helps the user discuss and draft letters, identify the correct recipient, review the final message, authenticate the sending action, and transmit the message through a user-authorized email provider.

## User Direction

The user does not want the system connected to their primary Gmail account. A separate email account may be acceptable for experimentation. Outlook was identified as a possible initial path because the user has not yet figured out how to achieve this workflow through Gmail or Gemini.

The user wants agentic capability while retaining a deliberate authentication step, potentially involving a passkey, fingerprint, device sensor, or PIN.

## Inventory

- **Project:** Conversational Letter Secretary.
- **Research question:** Whether Outlook can provide a practical, limited, authenticated sending workflow.
- **Prototype direction:** Start with plain-text email, one designated account, explicit review, and explicit approval for each send.
- **Related project:** One-Number AI Secretary.

## Decisions and Constraints

- Do not connect the user's primary Gmail account in the initial experiment.
- Do not store passwords, biometric data, or passkey private keys in the APO repository.
- Do not treat a draft as authorization to send.
- Verify recipient identity and address separately from authenticating the user.
- Keep provider-specific integration details marked as unknown until tested.
- Preserve existing APO projects and do not modify the repository root README as part of this archive.

## Evidence Classification

- **PROPOSED:** The overall conversational drafting and authenticated sending workflow.
- **KNOWN:** Microsoft documents passkeys and alternative account verification methods for Microsoft accounts.
- **UNKNOWN:** Exact integration permissions, account setup requirements, ability to force fresh approval, and available delivery reporting.
- **TESTED:** No end-to-end send test completed.

## Next Action

Inspect the available Outlook integration and account-connection process before choosing between a direct ChatGPT workflow and a separate application using an email API.
