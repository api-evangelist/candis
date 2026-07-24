---
name: Export approved invoices and download the files
description: Create a Candis export of approved postings, poll it to completion, list its postings, and download the resulting PDF/XML files for your accounting/ERP system.
api: openapi/candis-openapi.json
operations:
  - createExport
  - getExport
  - getExportPostings
  - downloadFile
---

# Export approved invoices from Candis

Use this flow to pull approved, export-ready data out of Candis and into an accounting solution or ERP.

## Prerequisites
- An OAuth2 access token with the `exports` scope (see `authentication/candis-authentication.yml`). Send it as `Authorization: Bearer {access_token}`.
- Your `organizationId` (the connected organization slug). All paths are under `https://api.candis.io/v1/organizations/{organizationId}`.

## Steps

1. **Create the export** — `createExport`
   `POST /v1/organizations/{organizationId}/exports`
   Body (optional): `{ "entityType": "DOCUMENT" }` — one of `DOCUMENT`, `REIMBURSEMENT_ITEM`, `CARD_TRANSACTION` (defaults to `DOCUMENT`).
   The response returns `{ id, postingsCount, status, createdAt }` with initial `status: "EXPORTING"`.
   If there is nothing to export you get `errorCode: EXPORTABLE_POSTINGS_NOT_FOUND` — stop.

2. **Poll for completion** — `getExport`
   `GET /v1/organizations/{organizationId}/exports/{exportId}` using the `id` from step 1.
   Repeat with backoff until `status` leaves `EXPORTING`. Respect the 500 req/min org rate limit; on `429`/`TOO_MANY_REQUEST` honor the `Retry-After` header.

3. **List the exported postings** — `getExportPostings`
   `GET /v1/organizations/{organizationId}/exports/{exportId}/postings`.
   Paginate with `offset`/`limit` (max `limit` is 50). Split postings carry a `type` (`ITEM` vs supplementary charge) and three-way-match metadata (`purchaseOrderMetadata`, `goodsReceiptMetadata`, `additionalDeliveryCostsMetadata`).

4. **Download the files** — `downloadFile`
   `GET /v1/organizations/{organizationId}/files/{fileId}` to retrieve each PDF or XML by id.
   `FILE_NOT_FOUND` / `FAILED_TO_FETCH_DOWNLOAD_URL` mean the file is not ready or retrievable — retry.

## Rules
- Exports are immutable once created: accounts-payable number and general ledger account cannot be changed after an export exists.
- Handle the Candis error envelope `{ errorCode, message, requestId, errors[] }`; log `requestId` for support.
- For DATEV/accounting-grade data always use the Export API (not the Invoice Data API, which is not export-complete).
