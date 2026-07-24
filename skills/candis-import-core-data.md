---
name: Import and update master core data (idempotent upsert)
description: Push general ledger accounts and cost dimensions from a third-party system into Candis using the idempotent Core Data import endpoints, then check the import status logs.
api: openapi/candis-openapi.json
operations:
  - createGeneralLedgerAccounts
  - updateGeneralLedgerAccounts
  - createCostCenter
  - updateCostCenter
  - getImportLogs
---

# Import master core data into Candis

Use this flow when a third-party system (ERP/accounting) is the leading system for master data and you need Candis to mirror it.

## Prerequisites
- An OAuth2 access token with the `core_data` scope (`Authorization: Bearer {access_token}`).
- Your `organizationId`. Base: `https://api.candis.io/v1/organizations/{organizationId}`.

## Steps

1. **Create general ledger accounts** — `createGeneralLedgerAccounts`
   `POST /v1/organizations/{organizationId}/imports/general-ledger-accounts`.
   For each account, contact name and accounts-payable number are the mandatory identifiers.

2. **Update general ledger accounts** — `updateGeneralLedgerAccounts`
   `PUT /v1/organizations/{organizationId}/imports/general-ledger-accounts`.

3. **Create / update cost dimensions** — `createCostCenter` / `updateCostCenter`
   `POST` / `PUT /v1/organizations/{organizationId}/imports/cost-centers` to import cost centers and cost objects.

4. **Check import status** — `getImportLogs`
   `GET /v1/organizations/{organizationId}/imports/{processId}` to get the status summary of an import request (which records succeeded/failed and why).

## Rules — idempotency
- **Core Data imports are idempotent by business key.** Re-importing a record with the same key (e.g. the same order/account number) **updates the existing record instead of creating a duplicate**. There is no `Idempotency-Key` header — idempotency is a property of these import endpoints (see `conventions/candis-conventions.yml`). Safe to retry.
- Validation failures come back in the error envelope's `errors[]` with the offending `index`/`property` (`BAD_INPUT`). Fix and re-send — the re-send upserts.
- Respect the 500 req/min per-organization rate limit; batch records into single import calls where possible and back off on `429`.
