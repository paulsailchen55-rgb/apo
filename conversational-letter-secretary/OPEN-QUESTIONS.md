# Open Questions

## Provider and Account

- Can an Outlook personal account be created and used without linking the user's primary phone number?
- What recovery options are available if phone verification is unavailable or undesirable?
- Which Outlook integration is available in ChatGPT, and what exact read/write permissions does it require?
- Can access be limited to sending rather than reading the entire mailbox?

## Authorization

- Can every send require a fresh explicit approval?
- Can approval use an operating-system passkey, fingerprint, face recognition, or device PIN?
- Does the integration expose a clear confirmation step before transmission?
- What happens if the user changes the message after approval but before sending?

## Recipient Safety

- How should the system verify that the intended person and email address match?
- How should ambiguous names, outdated addresses, aliases, and group addresses be handled?
- Should first-time recipients require an additional confirmation step?

## Privacy and Records

- What draft, message, recipient, and audit data is retained by each provider or integration?
- Can sensitive drafts be kept locally or deleted after sending?
- How should the project distinguish provider acceptance, delivery, bounce, and read status?

## Technical Development

- Is a ChatGPT integration sufficient for the first experiment, or is a separate application needed?
- Would OAuth authorization be sufficient, or is a custom approval service required?
- Can WebAuthn/passkeys be implemented without storing biometric information?
- What is the minimum viable prototype that can be tested safely?

## Status

These questions remain unresolved. No end-to-end implementation or sending test has been completed as part of this archive.
