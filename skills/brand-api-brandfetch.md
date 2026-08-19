---
name: Brandfetch
description: Use when retrieving brand data (logos, colors, fonts, company details), searching for brands by name, enriching transactions with merchant data, or integrating brand context into AI agents and applications. Agents should reach for this skill when building features that need verified brand assets, company information, or when grounding LLMs with real-time brand context.
metadata:
    mintlify-proj: brandfetch
    version: "1.0"
---

# Brandfetch Skill

## Product summary

Brandfetch is a brand data API platform that provides programmatic access to company logos, colors, fonts, company details, and brand context. Agents use it to retrieve verified brand assets in real-time, search for brands by name, enrich transaction data with merchant information, and ground AI models with structured brand context. The primary APIs are Brand API (logos, colors, fonts, company data), Logo API (CDN-based logo delivery), Brand Search API (name-to-domain matching), Brand Context API (LLM-ready brand profiles), and Transaction API (merchant identification from payment text). Authentication uses Bearer tokens (API key) for REST endpoints or client IDs for Logo API and Brand Search API. The main endpoint is `https://api.brandfetch.io/v2/` with a CDN at `https://cdn.brandfetch.io/`. See [https://docs.brandfetch.com](https://docs.brandfetch.com) for full documentation.

## When to use

Reach for this skill when:

- **Retrieving brand assets**: You need logos, colors, fonts, or company details for a domain, stock ticker, ISIN, or crypto symbol.
- **Searching for brands**: You have a company name but need to find its domain or logo (use Brand Search API).
- **Enriching transactions**: You have raw payment text (e.g., "STARBUCKS 1523 OMAHA NE") and need to identify the merchant brand (Transaction API, Enterprise only).
- **Building brand context for AI**: You're grounding an LLM with structured brand information like mission, positioning, voice, and visual style (Brand Context API).
- **Embedding logos in UI**: You need to display logos that auto-update when brands change (Logo API CDN).
- **Listening to brand updates**: You need real-time notifications when a brand's data changes (webhooks, Enterprise only).
- **Integrating with AI assistants**: You're connecting Claude, Cursor, or other MCP-compatible tools to brand data (Brandfetch MCP).

## Quick reference

### Authentication methods

| Method | Use case | Format |
|--------|----------|--------|
| **API Key (Bearer)** | Brand API, Brand Context API, Transaction API | `Authorization: Bearer <api_key>` in header |
| **Client ID** | Logo API, Brand Search API | `?c=<client_id>` query parameter |
| **OAuth** | Brandfetch MCP (AI assistants) | Browser sign-in or MCP token |

### Identifier types (Brand API)

| Type | Example | Route |
|------|---------|-------|
| Domain | `nike.com` | `/v2/brands/domain/nike.com` |
| Stock/ETF ticker | `NKE`, `QQQ` | `/v2/brands/ticker/NKE` |
| ISIN | `US6541061031` | `/v2/brands/isin/US6541061031` |
| Crypto symbol | `BTC`, `ETH` | `/v2/brands/crypto/BTC` |
| Auto-detect (legacy) | `nike.com` | `/v2/brands/nike.com` |

### Logo API URL structure

```
https://cdn.brandfetch.io/{type}/{identifier}/{path_params}?c={client_id}
```

**Path parameters** (all optional):
- `w/{width}` — Logo width (aspect ratio preserved)
- `h/{height}` — Logo height (aspect ratio preserved)
- `theme/{light|dark}` — Theme variant
- `type/{icon|logo|symbol}` — Logo type (default: icon)
- `fallback/{brandfetch|transparent|lettermark|404}` — Fallback when logo unavailable

**Example**: `https://cdn.brandfetch.io/domain/nike.com/w/128/h/128/theme/dark/type/icon?c=CLIENT_ID`

### API endpoints summary

| Endpoint | Method | Purpose | Auth |
|----------|--------|---------|------|
| `/v2/brands/{type}/{id}` | GET | Fetch brand data (logos, colors, fonts, company info) | API Key |
| `/v2/context/{domain}` | GET | Get LLM-ready brand context (mission, positioning, voice) | API Key |
| `/v2/search/{name}` | GET | Search brands by name | Client ID |
| `/v2/brands/transaction` | POST | Identify merchant from transaction text | API Key |
| `https://cdn.brandfetch.io/` | GET | Embed logos directly in HTML | Client ID |

### Quotas and rate limits

| API | Free tier | Rate limit | Notes |
|-----|-----------|-----------|-------|
| Brand API | 100 requests/month | 100 req/sec sustained, 30k/5min burst | Overage billing available |
| Logo API | 500k requests/month | 1k req/5min per IP, 2.4k/5min per customer | Soft limit, no immediate block |
| Brand Search API | 500k requests/month | 200 req/5min per IP | Use debounce for autocomplete |
| Brand Context API | 100 requests/month | 100 req/sec sustained, 30k/5min burst | Overage billing available |
| Transaction API | Shared with Brand API | Shared quota | Enterprise only |

## Decision guidance

### When to use Brand API vs Brand Search API

| Scenario | Use Brand API | Use Brand Search API |
|----------|---------------|---------------------|
| You have a domain, ticker, ISIN, or crypto symbol | ✓ | |
| You only have a company name | | ✓ |
| You need logos, colors, fonts, company details | ✓ | |
| You need to build autocomplete/search UI | | ✓ |
| You need real-time brand data | ✓ | ✓ |

**Workflow**: Use Brand Search API to convert a company name to a domain, then call Brand API with that domain to get full brand data.

### When to use Logo API CDN vs Brand API logos

| Scenario | Use Logo API CDN | Use Brand API |
|----------|-----------------|---------------|
| Embedding logos directly in HTML `<img>` tags | ✓ | |
| Logos must auto-update when brand changes | ✓ | |
| You need logos in your backend/API response | | ✓ |
| You need multiple logo formats in one call | | ✓ |
| You need colors, fonts, company data too | | ✓ |
| You want to cache logos locally | | ✓ |

### When to use Brand Context API

| Scenario | Use Brand Context API | Use Brand API |
|----------|----------------------|---------------|
| Grounding an LLM with brand information | ✓ | |
| Generating on-brand content | ✓ | |
| You need mission, positioning, voice, audience | ✓ | |
| You need logos, colors, fonts, company data | | ✓ |
| You want Markdown output for prompts | ✓ | |
| You need structured JSON response | ✓ | ✓ |

### When to use Transaction API

| Scenario | Use Transaction API |
|----------|---------------------|
| You have raw payment text (bank/credit card statement) | ✓ |
| You need to identify the merchant brand | ✓ |
| You have a domain/ticker already | Use Brand API instead |
| **Availability** | Enterprise only |

## Workflow

### 1. Retrieve brand data by domain

1. **Get your API key** from [https://developers.brandfetch.com/register](https://developers.brandfetch.com/register)
2. **Make a GET request** to `/v2/brands/domain/{domain}` with `Authorization: Bearer <api_key>` header
3. **Parse the response** to extract logos (with formats and themes), colors, fonts, company details (employees, founded year, industries, location)
4. **Test with brandfetch.com** first (free, doesn't count toward quota)
5. **Deploy** by replacing `brandfetch.com` with your target domain

**Example**:
```bash
curl --request GET \
  --url https://api.brandfetch.io/v2/brands/domain/nike.com \
  --header 'Authorization: Bearer YOUR_API_KEY'
```

### 2. Search for a brand by name

1. **Get your client ID** from the Developer Portal
2. **Make a GET request** to `/v2/search/{name}?c={client_id}`
3. **Parse results** to find the matching brand (returns icon, name, domain, claimed status, brandId)
4. **Use the domain** from results to call Brand API for full data
5. **Implement debounce** in autocomplete UI to avoid rate limiting (200 req/5min per IP)

**Example**:
```bash
curl --request GET \
  "https://api.brandfetch.io/v2/search/Nike?c=YOUR_CLIENT_ID"
```

### 3. Embed a logo in HTML

1. **Get your client ID** from the Developer Portal
2. **Construct the CDN URL** using the pattern: `https://cdn.brandfetch.io/{type}/{identifier}/{params}?c={client_id}`
3. **Embed directly in `<img>` tag** (hotlinking required)
4. **Add optional parameters** for sizing, theme, type, fallback
5. **Verify** the logo renders and updates when brand changes

**Example**:
```html
<img
  src="https://cdn.brandfetch.io/domain/nike.com/w/128/h/128/theme/dark/type/icon?c=YOUR_CLIENT_ID"
  alt="Nike logo"
/>
```

### 4. Get brand context for AI/LLM

1. **Get your API key**
2. **Make a GET request** to `/v2/context/{domain}` with `Authorization: Bearer <api_key>` header
3. **Set Accept header** to `application/json` (structured) or `text/markdown` (LLM-ready)
4. **Parse response** for identity (tagline, mission, description), positioning (value prop, audience, products), and brand (voice, visual style)
5. **Use Markdown response** directly in LLM prompts for on-brand content generation

**Example**:
```bash
curl --request GET \
  --url https://api.brandfetch.io/v2/context/brandfetch.com \
  --header 'Authorization: Bearer YOUR_API_KEY' \
  --header 'Accept: text/markdown'
```

### 5. Identify a merchant from transaction text

1. **Get your API key** (Enterprise plan required)
2. **Make a POST request** to `/v2/brands/transaction` with transaction label and country code
3. **Send JSON body**: `{"transactionLabel": "STARBUCKS 1523 OMAHA NE", "countryCode": "US"}`
4. **Parse response** to get brand name, domain, logo, company details
5. **Use the domain** for follow-up Brand API calls if needed

**Example**:
```bash
curl --request POST \
  --url https://api.brandfetch.io/v2/brands/transaction \
  --header 'Authorization: Bearer YOUR_API_KEY' \
  --header 'Content-Type: application/json' \
  --data '{"transactionLabel": "STARBUCKS 1523 OMAHA NE", "countryCode": "US"}'
```

## Common gotchas

- **Naming collisions**: Always use explicit type routes (`/v2/brands/domain/nike.com` not `/v2/brands/nike.com`) to avoid auto-detection errors when a ticker matches a domain.
- **Logo API hotlinking required**: Logo CDN URLs must be embedded directly in HTML `<img>` tags. Programmatic access (downloading, caching without permission) is blocked. Set your `Referrer-Policy` header to `origin`, `origin-when-cross-origin`, `strict-origin`, `strict-origin-when-cross-origin`, or `unsafe-url`.
- **Logo URLs expire**: Brand Search API returns logo URLs that expire after 24 hours. Don't cache them; refetch when needed.
- **Client ID vs API Key confusion**: Logo API and Brand Search API use client IDs (query parameter `?c=`). Brand API, Brand Context API, and Transaction API use API keys (Bearer token). Don't mix them up.
- **Quota exhaustion returns 429**: When you hit your monthly quota or throughput limit, the API returns HTTP 429. Set a spending limit in the dashboard to prevent overage charges.
- **Transaction API is Enterprise only**: Don't attempt to use `/v2/brands/transaction` on free or standard plans.
- **Webhooks are Enterprise only**: Real-time brand update notifications require an Enterprise plan.
- **Brand Context API live resolution is slow**: By default, unknown domains are resolved live (can take seconds). Use `?cachedOnly=true` for instant responses if the domain is already cached.
- **Auto-detect order matters**: Without a type prefix, identifiers are resolved as: domain → ticker → ISIN → crypto. A ticker that matches a domain name will be treated as a domain.
- **Overage billing not on free plan**: You can't enable overage billing on the free tier. Upgrade to a paid plan first.
- **Rate limit per IP, not per key**: Logo API and Brand Search API rate limits are per IP address, not per API key. Multiple keys from the same IP share the limit.

## Verification checklist

Before submitting work with Brandfetch integration:

- [ ] **Authentication**: Verify API key or client ID is correctly passed (Bearer header for API key, `?c=` query param for client ID)
- [ ] **Identifier type**: Confirm you're using explicit type routes (`/domain/`, `/ticker/`, `/isin/`, `/crypto/`) to avoid collisions
- [ ] **Quota monitoring**: Check `x-api-key-quota` and `x-api-key-approximate-usage` response headers; ensure you're not approaching limits
- [ ] **Error handling**: Confirm 404 (brand not found), 401 (invalid key), and 429 (quota exceeded) are handled gracefully
- [ ] **Logo hotlinking**: If using Logo API, verify logos are embedded in `<img>` tags and `Referrer-Policy` header is set correctly
- [ ] **Rate limiting**: For autocomplete, confirm debounce is implemented (Brand Search API: 200 req/5min per IP)
- [ ] **Test domain**: Verify integration works with `brandfetch.com` before deploying to production
- [ ] **Response parsing**: Confirm your code correctly extracts logos (formats, themes), colors, fonts, and company data from the response
- [ ] **Caching strategy**: If caching brand data, ensure you're not caching Logo API URLs (they expire after 24 hours)
- [ ] **Error messages**: Verify API error responses are logged and user-facing errors are clear (e.g., "Brand not found" vs "API error")

## Resources

- **Full documentation and page listing**: [https://docs.brandfetch.com/llms.txt](https://docs.brandfetch.com/llms.txt)
- **Brand API reference**: [https://docs.brandfetch.com/reference/brand-api-domain](https://docs.brandfetch.com/reference/brand-api-domain)
- **Logo API parameters**: [https://docs.brandfetch.com/logo-api/parameters](https://docs.brandfetch.com/logo-api/parameters)
- **Brand Context API reference**: [https://docs.brandfetch.com/reference/brand-context-api](https://docs.brandfetch.com/reference/brand-context-api)

---

> For additional documentation and navigation, see: https://docs.brandfetch.com/llms.txt