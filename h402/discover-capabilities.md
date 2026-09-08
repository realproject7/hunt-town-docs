# Discover Capabilities

h402 is **task-first**: you look for the outcome you want, not the vendor who provides it.
Capabilities are named `category/action` and indexed in the **catalog**.

## Naming

Every capability describes an outcome:

- `web/search`
- `ai/image-generate`
- `crypto/price`
- `research/web-task`

Categories currently span `ai`, `business`, `crypto`, `domains`, `finance`, `maps`,
`people`, `predictions`, `real-estate`, `research`, `security`, `social`, `travel`,
`utilities`, `weather`, and `web`.

## From the CLI

```
h402 search "web search"           # find capabilities by keyword
h402 show web/search               # inspect a capability and its providers
h402 quote web/search --json '{}'  # price a call without paying
```

`h402 show` is the important one before a first call: it lists each provider, its price,
its native input schema, and its stored response sample.

## From the catalog API

Agents and tooling can query the catalog directly:

| Endpoint | Purpose |
| --- | --- |
| `GET /api/catalog` | Compact list of every public capability |
| `GET /api/catalog/search?q=` | Ranked search |
| `GET /api/catalog/routes/{id}` | Full detail: every enabled provider plus the recommended default |
| `GET /llms.txt` | Single-file onboarding doc with the catalog inlined as plain text |
| `GET /openapi.json` | OpenAPI specification |
| `GET /.well-known/ai-catalog.json` | Agentic Resource Discovery (ARD) manifest |

## What a capability tells you before you pay

For each provider of a capability the catalog exposes:

- the **price** per call (provider price plus h402's fee), in Base USDC,
- the provider's **native input schema** and an example input,
- a **stored real-response sample** from an actual paid call, and
- its **status** — only paid-tested providers are listed as enabled.

That is enough to choose a provider and predict both the cost and the response shape before
committing. See [Providers & Verification](providers.md).

## A curated index, not a crawler

h402 **self-indexes only**. It does not crawl the web for endpoints or refer callers out to
third-party registries; providers are curated into the catalog and verified before they
appear. That is what makes "everything in the catalog has been paid-tested" a claim the
market can actually keep.
