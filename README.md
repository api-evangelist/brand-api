# Brand API (Brandfetch) (brand-api)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Brandfetch provides programmatic access to brand assets and company data through a suite of APIs. The Brand API retrieves logos, color schemes, fonts, images, and firmographic information for any company via domain, stock ticker, ISIN code, or crypto symbol. The Logo Link API serves logos via CDN with support for multiple formats, themes, and sizes. The Brand Search API enables autocomplete experiences by matching brand names to their domains and identifiers. All APIs support Bearer token authentication with free access for development.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/brand-api/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/brand-api/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Brands
- Logos
- Brand Assets
- Company Data
- Firmographics

## Timestamps

- **Created:** 2024-03-30
- **Modified:** 2026-04-21

## APIs

### Brandfetch Brand API

Brand API provides programmatic access to any company's brand assets through a single API call. Returns the latest logos, color schemes, fonts, images, and firmographic information. Supports lookup by domain (e.g. nike.com), stock/ETF ticker (e.g. NKE), ISIN code, or crypto symbol (e.g. BTC). Base endpoint: GET /v2/brands/{identifier}. Authentication via Bearer token. Free sandbox testing available on the brandfetch.com domain.

- **Human URL:** [https://docs.brandfetch.com/docs/brand-api](https://docs.brandfetch.com/docs/brand-api)

#### Tags

- Brands
- Logos
- Colors
- Fonts
- Firmographics

#### Properties

- [OpenAPI](openapi/brandfetch-brand-api.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.brandfetch.com/docs/brand-api)

### Brandfetch Logo Link API

Logo Link delivers brand logos directly via CDN URL embedding. Supports lookup by domain, stock ticker, crypto symbol, or ISIN. Parameters include logo type (icon, symbol, logo), theme (light/dark), height/width, format (webp, png, jpg, svg), and fallback behavior. Base CDN URL: https://cdn.brandfetch.io/{identifier}?c=CLIENT_ID. Free with fair-use rate limits; no attribution required.

- **Human URL:** [https://docs.brandfetch.com/docs/logo-link](https://docs.brandfetch.com/docs/logo-link)

#### Tags

- Logos
- CDN
- Brand Assets

#### Properties

- [Documentation](https://docs.brandfetch.com/docs/logo-link)

### Brandfetch Brand Search API

Brand Search API matches brand names to their corresponding domain URLs and unique identifiers, enabling rich autocomplete experiences. Endpoint: GET https://api.brandfetch.io/v2/search/:name. Authentication via Client ID query parameter. Free to use; no attribution required.

- **Human URL:** [https://docs.brandfetch.com/docs/brand-search-api](https://docs.brandfetch.com/docs/brand-search-api)

#### Tags

- Brand Search
- Autocomplete
- Domain Matching

#### Properties

- [Documentation](https://docs.brandfetch.com/docs/brand-search-api)

## Common Properties

- [GitHub Organization](https://github.com/brandfetch)
- [LinkedIn](https://www.linkedin.com/company/brandfetch)
- [Customers](https://brandfetch.com/developers/customers)
- [Pricing](https://brandfetch.com/developers/pricing)
- [Getting Started](https://docs.brandfetch.com/docs/getting-started)
- [Webhooks](https://docs.brandfetch.com/docs/webhooks/overview)
- [Event Types](https://docs.brandfetch.com/docs/webhooks/event-types)
- [Support](https://docs.brandfetch.com/support/getting-help)
- [Issues](https://docs.brandfetch.com/support/report-inaccuracies)
- [Recipes](https://docs.brandfetch.com/recipes/overview)
- [Documentation](https://docs.brandfetch.com/reference/overview)
- [Sandbox](https://docs.brandfetch.com/docs/brand-api#testing-sandbox)
- [Changelog](https://docs.brandfetch.com/changelog/2024)
- [Login](https://developers.brandfetch.com/)
- [Sign Up](https://developers.brandfetch.com/register)
- [L L Ms Txt](https://docs.brandfetch.com/llms.txt)

## Maintainers

**FN:** API Evangelist
**Email:** info@apievangelist.com
