---
name: Model and populate Encharge custom objects
description: >-
  Define a custom object schema (companies, invoices, anything), add fields and
  associations to it, then upsert instances and associate them with people.
api: openapi/encharge-customobjectsschema-api-openapi.yml
operations:
  - GetCustomObjectsSchema
  - CreateCustomObjectSchema
  - CreateObjectFields
  - DefineCustomObjectsAssociationSchema
  - CreateOrUpdateCustomObjects
  - SearchCustomObjects
  - GetCustomObjectByExternalId
  - AssociateObjectsByDefaultAssociation
generated: '2026-08-13'
method: generated
source: openapi/_original/encharge-openapi.yml + data-model/encharge-data-model.yml
---

# Model and populate Encharge custom objects

Base URL: `https://api.encharge.io/v1`. Custom objects are a **Premium plan**
feature — on Growth these operations are not available to the account.

Scopes: `account:write` for object data, `personFields:write` for schema field
edits.

## Steps

1. **Inspect what exists** — `GetCustomObjectsSchema` (`GET /schemas`) lists
   every object type on the account, including the built-in `company`.
2. **Define the type** — `CreateCustomObjectSchema` (`POST /schemas`) with
   `name`, `displayNameSingular`, `displayNamePlural`, `primaryField` and
   `searchableFields`. Only `searchableFields` are reachable later through
   `SearchCustomObjects`, so choose them at design time.
3. **Add fields** — `CreateObjectFields`
   (`POST /schemas/{objectName}/fields`); amend with `EditObjectField`
   (`PATCH /schemas/{objectName}/fields/{fieldName}`).
4. **Declare associations** — `DefineCustomObjectsAssociationSchema`
   (`POST /schemas/associations`) with `fromObject`, `toObject`, `type` and
   `name`. An association must be declared before instances can be linked.
5. **Upsert instances** — `CreateOrUpdateCustomObjects`
   (`PUT /objects/{objectName}`). Pass your own `externalId` so the call is an
   upsert-by-key rather than a duplicate create; you can then read it back with
   `GetCustomObjectByExternalId`.
6. **Link to people** — `AssociateObjectsByDefaultAssociation`
   (`POST /objects/{objectName}/{id}/associations/default/{targetObjectName}/{targetId}`)
   or the explicit `AssociateCustomObjects` when you want a named association.
7. **Find them again** — `SearchCustomObjects`
   (`GET /objects/{objectName}/search?query=...`), or count with
   `GetCustomObjectsCount` / `GetCustomObjectsInSegmentCount`.

## Shortcut from your backend

The Ingest API's special `group` event
(`POST https://ingest.encharge.io/v1/` with `"type": "group"`, `objectType`,
`properties` and a `user` block) creates or updates an object **and** associates
a person with it in one call — but the schema must already exist. Use it for
high-volume backend sync; use the REST operations above for schema management.

## Cautions

- `DeleteCustomObjectSchema` (`DELETE /schemas/{objectName}`) removes the object
  *definition*. Destructive — confirm with a human first.
- Ids are numeric, not prefixed strings, so an id alone does not tell you which
  object type it belongs to; always carry `objectName` alongside it.
