# Brand API (Brandfetch)

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

Brandfetch provides programmatic access to brand assets and company data through a suite of APIs. The Brand API retrieves logos, color schemes, fonts, images, and firmographic information for any company via domain, stock ticker, ISIN code, or crypto symbol. The Logo Link API serves logos via CDN with support for multiple formats, themes, and sizes. The Brand Search API enables autocomplete experiences by matching brand names to their domains and identifiers. The Brand Context API returns an LLM-ready narrative profile — identity, positioning, voice and visual style — for grounding agents, and the Transaction API resolves raw payment descriptors into merchant identity. A hosted MCP server at mcp.brandfetch.io exposes the same capabilities as seven agent tools over OAuth, and an Enterprise GraphQL endpoint carries the account, webhook and brand-monitoring plane. REST authenticates with Bearer API keys; the Logo and Search APIs use a public, embeddable Client ID.

**Areas:** Brands · Logo · Brand Assets · Company Data · Firmographics · Brand Context · Merchant Enrichment · Agent Tools · A2A

## Brand API (Brandfetch) on APIs.io

Everything profiled for Brand API (Brandfetch) is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/brand-api/](https://apis.io/providers/brand-api/)** — or go straight to one of the APIs or properties below.

### APIs (8)

- [Brandfetch MCP Server](https://apis.io/apis/brand-api/brandfetch-mcp/) — Hosted, remote, streamable-HTTP MCP server exposing seven Brandfetch tools — brand_search, get_brand, get_brand_context, enrich_transaction,…
- [Brandfetch GraphQL API](https://apis.io/apis/brand-api/brandfetch-graphql/) — Enterprise GraphQL endpoint carrying the account plane the REST API does not expose — organizations, API keys, request logs, quotas, billing, webhook…
- [Brandfetch Logo Link API](https://apis.io/apis/brand-api/brandfetch-logo-link-api/) — Logo Link delivers brand logos directly via CDN URL embedding. Supports lookup by domain, stock ticker, crypto symbol, or ISIN. Parameters include logo type…
- [Brandfetch Brand Search API](https://apis.io/apis/brand-api/brandfetch-brand-search-api/) — Brand Search API matches brand names to their corresponding domain URLs and unique identifiers, enabling rich autocomplete experiences. Endpoint: GET…
- [Brand API (Brandfetch) Brands API](https://apis.io/apis/brand-api/brand-api-brands-api/) — The Brands API from Brand API (Brandfetch) — the tag-split refinement of the earlier single-operation harvest, superseded by the full nine-operation spec on…
- [Brand API (Brandfetch) Context API](https://apis.io/apis/brand-api/brand-api-context-api/) — The context API from Brand API (Brandfetch) — 1 operation(s) for context.
- [Brand API (Brandfetch) Search API](https://apis.io/apis/brand-api/brand-api-search-api/) — The Search API from Brand API (Brandfetch) — 1 operation(s) for search.
- [Brand API (Brandfetch) Viewer API](https://apis.io/apis/brand-api/brand-api-viewer-api/) — The viewer API from Brand API (Brandfetch) — 1 operation(s) for viewer.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Brand Api Webhooks](https://apis.io/asyncapis/brand-api/brand-api-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [brandfetch](https://apis.io/servers/brand-api/brandfetch/)

#### Collections (1)

Postman and Open Collection request collections.

- [Brandfetch Brand Brands API](https://apis.io/collections/brand-api/open-brand-api-brands-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Brand Api Brandfetch Overlay](https://apis.io/overlays/brand-api/brand-api-brandfetch-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Brand Api Authentication](https://apis.io/security/brand-api/brand-api-authentication/)
- [Brand Api Domain Security](https://apis.io/security/brand-api/brand-api-domain-security/)
- [Brand Api Trust Center](https://apis.io/security/brand-api/brand-api-trust-center/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Brand Api Scopes](https://apis.io/scopes/brand-api/brand-api-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Brand Api Plans Pricing](https://apis.io/plans/brand-api/brand-api-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Brand Api Rate Limits](https://apis.io/rate-limits/brand-api/brand-api-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Brand Api Finops](https://apis.io/finops/brand-api/brand-api-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.brandfetch.com/)
- [Getting started](https://docs.brandfetch.com/get-started)
- [API reference](https://docs.brandfetch.com/reference/overview)
- [Pricing](https://brandfetch.com/developers/pricing)
- [Sign up](https://developers.brandfetch.com/register)
- [Support](https://docs.brandfetch.com/support/getting-help)
- [Changelog](https://docs.brandfetch.com/changelog/overview)
- [Blog](https://brandfetch.com/blog)
- [Compliance](https://trust.brandfetch.com)
- [Terms of service](https://docs.brandfetch.com/support/terms-and-conditions)
- [GitHub](https://github.com/brandfetch)
- [Status](https://status.brandfetch.io)

## API Evangelist rating

**Kin Score 61.1** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 63.3 |
| Contract governance | 18.2 |
| Operational transparency | 65.8 |
| Developer ergonomics | 71.4 |
| Access clarity | 57.9 |

**Agent readiness 50.9** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | verified |
| Event Surface Described | yes |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | — |

**Regulatory alignment 32.1** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/brand-api/](https://apis.io/providers/brand-api/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Brand API (Brandfetch): the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/brand-api/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
