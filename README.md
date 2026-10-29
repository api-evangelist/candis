# Candis

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Candis is a Berlin-based fintech (founded 2015) offering an AI-driven financial process automation and accounts-payable platform for SMEs. It captures incoming invoices, reads invoice data via OCR (business partner, amount, date, IBAN), routes them through approval workflows, and exports approved postings to accounting systems and ERPs. As a licensed DATEV interface partner it also integrates with Sage and Wolters Kluwer, and supports three-way matching of invoices against purchase orders and goods receipts. Candis exposes a public REST API (developer.candis.io) with an Export API, Core Data API, and read-only Invoice, Reimbursement Item, and Purchase Request Data APIs, secured with OAuth2/OIDC and fronted by an official MCP server.

**Areas:** Company · Fintech · Accounts Payable · Spend Management · Invoice Management · Financial Process Automation · Accounting · DATEV · OCR · Germany

## Candis on APIs.io

Everything profiled for Candis is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/candis/](https://apis.io/providers/candis/)** — or go straight to one of the APIs or properties below.

### APIs (6)

- [Candis Core Data API](https://apis.io/apis/candis/candis-core-data-api/) — Import/update master data: general ledger accounts, cost dimensions, additional delivery costs.
- [Candis Exports API](https://apis.io/apis/candis/candis-exports-api/) — Export approved invoices and postings to accounting/ERP systems.
- [Candis Invoices API](https://apis.io/apis/candis/candis-invoices-api/) — Read and update invoice metadata.
- [Candis Organizations API](https://apis.io/apis/candis/candis-organizations-api/) — The Organizations API from Candis — 1 operation(s) for organizations.
- [Candis Purchase Requests API](https://apis.io/apis/candis/candis-purchase-requests-api/) — Read purchase request data.
- [Candis Reimbursements API](https://apis.io/apis/candis/candis-reimbursements-api/) — The Reimbursements API from Candis — 1 operation(s) for reimbursements.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [candis](https://apis.io/servers/candis/candis/)

#### Collections (6)

Postman and Open Collection request collections.

- [Candis Core Data API](https://apis.io/collections/candis/open-candis-core-data-api/)
- [Candis Core Data Exports API](https://apis.io/collections/candis/open-candis-exports-api/)
- [Candis Core Data Invoices API](https://apis.io/collections/candis/open-candis-invoices-api/)
- [Candis Core Data Organizations API](https://apis.io/collections/candis/open-candis-organizations-api/)
- [Candis Core Data Purchase Requests API](https://apis.io/collections/candis/open-candis-purchase-requests-api/)
- [Candis Core Data Reimbursements API](https://apis.io/collections/candis/open-candis-reimbursements-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Candis Openapi Overlay](https://apis.io/overlays/candis/candis-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Candis Authentication](https://apis.io/security/candis/candis-authentication/)
- [Candis Domain Security](https://apis.io/security/candis/candis-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Candis Scopes](https://apis.io/scopes/candis/candis-scopes/)

#### Rate limits (1)

Published request limits.

- [Candis Rate Limits](https://apis.io/rate-limits/candis/candis-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.candis.io/en)
- [Documentation](https://developer.candis.io/docs/getting-started)
- [Getting started](https://developer.candis.io/docs/getting-started)
- [API reference](https://developer.candis.io/reference)
- [Support](https://hilfe.candis.io/en)
- [Changelog](https://developer.candis.io/changelog)
- [Blog](https://www.candis.io/en/blog)
- [Privacy policy](https://www.candis.io/en/privacy-policy)
- [GitHub](https://github.com/CandisIO)
- [Status](https://status.candis.io)

## API Evangelist rating

**Kin Score 43.3** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 50.8 |
| Contract governance | 18.2 |
| Operational transparency | 39.5 |
| Developer ergonomics | 39.9 |
| Access clarity | 17.1 |

**Agent readiness 52.3** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 30.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/candis/](https://apis.io/providers/candis/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Candis: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/candis/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
