---
name: Subscribe to Encharge events with webhooks
description: >-
  Register an HTTPS endpoint against Encharge's event catalog, handle the
  delivered events, and tear the subscription down again.
api: openapi/encharge-webhooks-api-openapi.yml
operations:
  - CreateWebhook
  - DeleteWebhook
generated: '2026-08-13'
method: generated
source: >-
  openapi/_original/encharge-openapi.yml (Webhooks tag) +
  asyncapi/encharge-webhooks.yml
---

# Subscribe to Encharge events with webhooks

Base URL: `https://api.encharge.io/v1`. Requires the `account:write` scope (or
the account API key in `X-Encharge-Token`).

## Steps

1. **Choose the event name.** Encharge subscribes by *event name*, and several
   names are templated — you subscribe to the concrete string, not a pattern:

   | Event | Fires when |
   |---|---|
   | `newUser` | a person is created |
   | `updatedUser` | a person is updated (`changedFields` carries before/after) |
   | `unsubscribedUser` | a person unsubscribes from all email |
   | `added-tag-{tag}` | a person is tagged, e.g. `added-tag-signed-up` |
   | `removed-tag-{tag}` | a person is untagged, e.g. `removed-tag-demo` |
   | `native-form-submitted-{formId}` | a native form is submitted, e.g. `native-form-submitted-123` |
   | `newObject-{objectType}` | a custom object/company is created, e.g. `newObject-company` |
   | `updatedObject-{objectType}` | a custom object/company is updated, e.g. `updatedObject-invoice` |

2. **Create the subscription** — `CreateWebhook` (`POST /event-subscriptions`)
   with `eventType` and `url` (both required). Response is `201` with
   `{ "subscription": { "id": <number> } }`. **Store that id** — it is the only
   handle for deleting the subscription later, and there is no list operation to
   recover it.

3. **Receive.** Encharge POSTs the event to your `url`. There is **no signing
   secret, no signature header and no documented replay protection**, so treat
   the payload as untrusted: verify by re-reading the affected person through
   `GetSpecificPeople` before acting on anything consequential.

4. **Unsubscribe** — `DeleteWebhook` (`DELETE /event-subscriptions/{id}`),
   returns `204`.

## Notes and limits

- Webhook **payload schemas are not published** — only the subscription
  request/response is in the OpenAPI. Capture a real delivery before relying on
  a field.
- No retry policy or delivery log is documented.
- For a full firehose of account activity rather than named events, Encharge
  sells the **Activity Stream** add-on (POSTs every event, must be ack'd 2xx
  within 2 seconds) — see `asyncapi/encharge-webhooks.yml`.
