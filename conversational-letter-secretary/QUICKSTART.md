# Quickstart and Development Path

## Phase 1 — Define the Experiment

1. Create or designate an email account that is not the user's primary Gmail account.
2. Determine whether Outlook personal email or another Outlook configuration is appropriate.
3. Document account recovery options without relying exclusively on a phone number.
4. Enable a provider-supported passkey or other strong authentication method where available.

## Phase 2 — Verify Integration Capabilities

1. Inspect the available Outlook integration permissions.
2. Determine whether the integration can draft, send, and report send status.
3. Determine whether the user receives a meaningful approval prompt before sending.
4. Confirm what data the integration can read and whether access can be limited.
5. Do not connect the primary Gmail account.

## Phase 3 — Manual Safety Test

Use a test recipient or the user's own designated test mailbox.

- Draft a harmless message.
- Confirm the exact recipient and body.
- Approve sending deliberately.
- Verify the provider's response.
- Check whether the message arrived.
- Document any difference between provider acceptance and actual delivery.

## Phase 4 — Prototype Requirements

Potential implementation options:

- ChatGPT-connected Outlook workflow, if the required actions are available.
- A small self-hosted web application using an email API.
- A local or hosted approval screen with WebAuthn/passkey support.

The first implementation should not attempt autonomous recipient discovery, bulk sending, attachment handling, or background sending.

## Phase 5 — Expansion Questions

Only after the basic flow is tested should the project consider:

- Reusable recipient records
- Letter templates
- Draft history
- Attachments
- Multiple providers
- Scheduled sending
- Printed-letter workflows
- Voice input
- Integration with the One-Number AI Secretary
