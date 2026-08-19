---
name: Send a transactional email through Encharge
description: >-
  Send a templated, HTML or plain-text transactional email from an application,
  and handle the accepted/failed responses.
api: docs-only (no OpenAPI — the Transactional Email API is documented in prose)
operations: []
generated: '2026-08-13'
method: generated
source: >-
  https://docs.encharge.io/transactional-email-api/reference,
  https://docs.encharge.io/transactional-email-api/technical-overview,
  https://docs.encharge.io/transactional-email-api/authentication
---

# Send a transactional email through Encharge

`POST https://api.encharge.io/v1/emails/send`

> This endpoint is **not** in Encharge's published OpenAPI — the spec's
> `/emails` paths are the email-*template* CRUD surface. Everything below comes
> from the published reference page, so there are no `operationId`s to ground
> against. Requires the **Premium** plan.

## Authenticate

API key in the `token` query parameter or the `X-Encharge-Token` header. Get it
from <https://app.encharge.io/account/info>.

## Request body

Exactly **one** of `template`, `html` or `text` must be set:

| Field | Type | Notes |
|---|---|---|
| `template` | string | Name of an Encharge email template |
| `html` | string | HTML body |
| `text` | string | Plain-text body |
| `to` | string \| object | Recipient email, or `{ userId }` to reuse the stored address |
| `from` | string \| object | Sender email, or `{ email, name }`; overrides the template sender |
| `templateProperties` | object | Values substituted into `{{ merge_tags }}` in body and subject |
| `unsubscribeCheck` | boolean | Defaults to true — set false (carefully) to send to unsubscribed people |
| `UTMTags` | boolean | Set false to disable automatic UTM tagging |
| `cc` / `bcc` | string | Comma-separated addresses |
| `reply` | string \| object | Reply-to; defaults to `from` |

## Responses

- **202 Accepted** on success — acceptance, not delivery. There is no delivery
  receipt in the response; delivery outcomes surface as account activity
  (`sms-sent`, email open/click activity) rather than on this call.
- Failures return the standard envelope:

  ```json
  { "error": { "message": "Missing email content. Please pass `template`, `html` or `text`",
               "markdown": "...", "traceId": "9751fe70-0957-11eb-a6b8-3baf67de29f8" } }
  ```

  Log `traceId`.

## Side effects to know about

- Sending to an address that is not yet in the account **creates a person** —
  which consumes subscriber quota and can pull the recipient into flows.
- There are no published rate limits and no idempotency key; a retried send is
  a second send.
