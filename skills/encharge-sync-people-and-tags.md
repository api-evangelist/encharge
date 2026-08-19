---
name: Sync people and tags into Encharge
description: >-
  Create or update people in an Encharge account, look them up, tag and untag
  them, and unsubscribe them — the core contact-sync loop for the Encharge REST
  API.
api: openapi/encharge-people-api-openapi.yml
operations:
  - CreateUpdatePeople
  - GetSpecificPeople
  - GetAllPeople
  - AddTag
  - RemoveTag
  - UnsubscribePerson
  - ArchivePeople
generated: '2026-08-13'
method: generated
source: >-
  openapi/_original/encharge-openapi.yml + conventions/encharge-conventions.yml +
  errors/encharge-problem-types.yml
---

# Sync people and tags into Encharge

Base URL: `https://api.encharge.io/v1`

## Authenticate

Send the account API key in the `X-Encharge-Token` header (the `token` query
parameter also works and is what the docs use for the Transactional Email API).
The key is found at <https://app.encharge.io/account/info>.

OAuth 2 authorization-code is available instead, and is what Encharge expects if
you are building an app for *other* Encharge customers — client credentials are
issued manually, not self-serve. Scopes for this flow: `people:read`,
`people:write`.

## Steps

1. **Upsert the person** — `CreateUpdatePeople` (`POST /people`). A person is
   keyed by `email` or your own `userId`; sending either one again updates
   rather than duplicates. This is the only write-safety Encharge offers: there
   is **no `Idempotency-Key`**, so a retried POST with the same key is a second
   upsert, not a deduplicated replay.
2. **Read the person back** — `GetSpecificPeople` (`GET /people`) with `email`
   or `userId`. Use the `attributes` query parameter to select only the fields
   you need.
3. **Tag** — `AddTag` (`POST /tags`) returns `201`. Untag with `RemoveTag`
   (`DELETE /tags`), which returns `204`. Tags are plain strings; the account
   tag registry is managed separately via `GetAccountTags` /
   `CreateAccountTags`.
4. **Unsubscribe when asked** — `UnsubscribePerson`
   (`POST /people/unsubscribe`) returns `204`. Do this rather than deleting; it
   preserves suppression.
5. **Archive or delete** — `ArchivePeople` (`DELETE /people`) returns `204`.
   Destructive; require explicit human confirmation before calling it.

## Paging

Collection reads (`GetAllPeople`) take `limit` and `offset`, plus `sort` and
`order`. No cursor pagination, and no documented maximum page size — start at
`limit=100` and back off if responses slow.

## Errors

Encharge declares **no** 4xx/5xx responses in its OpenAPI. Failures come back as

```json
{ "error": { "message": "...", "markdown": "...", "traceId": "..." } }
```

Log `traceId` — it is the only correlation handle Encharge gives you and it is
what support will ask for. There are no published rate limits and no
`Retry-After`/`RateLimit-*` headers, so implement your own conservative
backoff on any non-2xx.
