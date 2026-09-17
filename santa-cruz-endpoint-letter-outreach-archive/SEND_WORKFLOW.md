# Send Workflow

## Source of truth

Use `MASTER_RECIPIENT_LIST.csv` as the campaign status source of truth for this archived working set.

## Statuses

- `VERIFIED — UNSENT — ELIGIBLE FOR NEXT BATCH`: may be included in a send-ready batch.
- `UNVERIFIED — UNSENT — DO NOT SEND YET`: requires verification before sending.
- `SENT — DO NOT RESEND`: never include in a future batch.
- `DO NOT USE`: never include in a future batch.

## Batch rules

1. Select only VERIFIED + UNSENT recipients.
2. Use exactly 10 recipients per send batch when at least 10 eligible recipients remain.
3. If fewer than 10 eligible recipients remain, use the actual number; do not fill gaps with guesses.
4. Put addresses in plain text, one per line.
5. Do not add a `BCC:` label or clickable/mailto formatting to the copy/paste address list.
6. Immediately after the addresses, use the exact approved subject and complete approved letter in `APPROVED_ENDPOINT_LETTER.md`.
7. Do not personalize or rewrite the approved letter unless explicitly requested.

## Status update rule

Generating, displaying, or copying a batch does **not** mark recipients as sent. Change a recipient to `SENT — DO NOT RESEND` only after explicit confirmation that the email was actually sent.

## Accuracy rule

Never invent, guess, autocomplete, or substitute an email address. When verification, duplication, status, or eligibility is uncertain, stop rather than assuming.

## Historical corrections preserved in this archive

- Pauline Seales (`paulineseales120@gmail.com`) is recorded as SENT and must not be reused.
- Santa Cruz County Grand Jury (`grandjury@scgrandjury.org`) is recorded as SENT and must not be reused.
- `gtfoscc@proton.me` is recorded as DO NOT USE because of a previously reported delivery problem.
- Christopher Platt and Brett Hoyer are recorded as SENT in the current master and are excluded from future batches.

## Verification boundary

Verification status in this file reflects the campaign working record. It does not claim that every unverified contact is invalid; it means only that the address was not established to the campaign's required verification standard at the time of archiving.
