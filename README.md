# Brand API / Brandfetch (brand-api)

Brandfetch provides programmatic access to brand assets and company data through a suite of APIs. The Brand API retrieves logos, color schemes, fonts, images, and firmographic information for any company via domain, stock ticker, ISIN code, or crypto symbol. The Logo Link API serves logos via CDN with support for multiple formats, themes, and sizes. The Brand Search API enables autocomplete experiences by matching brand names to their domains and identifiers.

**URL:** [https://raw.githubusercontent.com/api-evangelist/brand-api/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/brand-api/refs/heads/main/apis.yml)

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

Programmatic access to brand assets via single API call. Returns logos, color schemes, fonts, images, and firmographic data. Endpoint: `GET /v2/brands/{identifier}`. Supports domain, stock ticker, ISIN, and crypto symbol lookups. Bearer token authentication.

**Human URL:** [https://docs.brandfetch.com/docs/brand-api](https://docs.brandfetch.com/docs/brand-api)

#### Properties

- [OpenAPI](openapi/brandfetch-brand-api.yml)
- [Documentation](https://docs.brandfetch.com/docs/brand-api)
- [Sandbox](https://docs.brandfetch.com/docs/brand-api#testing-sandbox)

### Brandfetch Logo Link API

CDN-based logo delivery via URL embedding. Endpoint: `https://cdn.brandfetch.io/{identifier}?c=CLIENT_ID`. Supports logo types (icon, symbol, logo), themes (light/dark), formats (webp, png, jpg, svg), and fallback behaviors. Free with fair-use rate limits.

**Human URL:** [https://docs.brandfetch.com/docs/logo-link](https://docs.brandfetch.com/docs/logo-link)

### Brandfetch Brand Search API

Match brand names to domains and identifiers for autocomplete experiences. Endpoint: `GET https://api.brandfetch.io/v2/search/:name`. Authentication via Client ID query parameter. Free to use.

**Human URL:** [https://docs.brandfetch.com/docs/brand-search-api](https://docs.brandfetch.com/docs/brand-search-api)

## Common Properties

- [Customers](https://brandfetch.com/developers/customers)
- [Pricing](https://brandfetch.com/developers/pricing)
- [Getting Started](https://docs.brandfetch.com/docs/getting-started)
- [Webhooks](https://docs.brandfetch.com/docs/webhooks/overview)
- [Event Types](https://docs.brandfetch.com/docs/webhooks/event-types)
- [Support](https://docs.brandfetch.com/support/getting-help)
- [Issues](https://docs.brandfetch.com/support/report-inaccuracies)
- [Recipes](https://docs.brandfetch.com/recipes/overview)
- [Reference](https://docs.brandfetch.com/reference/overview)
- [Change Log](https://docs.brandfetch.com/changelog/2024)
- [Login](https://developers.brandfetch.com/)
- [Sign Up](https://developers.brandfetch.com/register)

## Authentication

- Brand API: Bearer token via `Authorization` header
- Logo Link API: Client ID via query parameter
- Brand Search API: Client ID via query parameter

## Identifier Types

Domain (nike.com), Stock/ETF ticker (NKE), ISIN code (US6541061031), Crypto symbol (BTC, ETH)

## Use Cases

B2B personalization, brand asset retrieval, company data enrichment, financial platform logos, crypto app branding, multi-tenant SaaS branding, brand autocomplete, CRM enrichment

## Maintainers

**FN:** API Evangelist

**Email:** info@apievangelist.com
