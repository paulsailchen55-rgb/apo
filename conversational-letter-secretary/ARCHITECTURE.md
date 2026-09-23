# Architecture

## Conceptual Components

### 1. Conversation and Drafting Layer

- Receives the user's instructions.
- Helps clarify purpose, audience, tone, facts, and requested action.
- Produces a draft while distinguishing user-provided facts from AI suggestions.

### 2. Review Layer

Displays:

- Recipient name
- Recipient email address
- Subject
- Complete message body
- Attachments, if any
- Any unresolved uncertainty or missing information

### 3. Recipient Verification Layer

The system should not infer that a similarly named person is the correct recipient. It should use a confirmed address book entry, a user confirmation, or another documented verification process.

### 4. Authorization Layer

The system should require a deliberate send approval. A future implementation may use a provider login, OAuth consent, passkey, device PIN, or biometric confirmation supported by the operating system and provider.

The application must not collect or store raw fingerprints, face data, passkey private keys, or email passwords.

### 5. Email Provider Adapter

The first provider candidate is Outlook. The design should keep the provider adapter replaceable so the project does not depend permanently on one service.

### 6. Audit and Outcome Layer

Record only the minimum necessary metadata, such as draft identifier, approved recipient, approval time, send request time, provider response, and status. Separate `send accepted by provider` from `delivered` and `read`.

## Initial Prototype Boundary

- One user
- One separately designated email account
- Plain-text email
- No automatic recurring sending
- No bulk distribution
- No attachments initially
- Manual recipient confirmation
- Explicit approval before every send

## Security Assumption

Authentication of the user and verification of the recipient are different controls. Both are required for safe operation.
