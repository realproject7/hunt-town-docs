# Discover Routes

h402 is **task-first**: you find capabilities by the task you want done, not by which
vendor provides it. Capabilities are organized as **routes** and indexed in the
**catalog**.

## The task-first naming convention

Every route is named `category/action`:

- `ai/image-generate`
- `ai/song-generate`
- `web/search`
- `research/web-task`

The name describes the **outcome**, and h402 maps it to a provider that fulfills it. This
is what lets an agent reason in terms of "I need an image generated" rather than "I need to
integrate Vendor X's image API, with Vendor X's auth, billing, and response shape."

## Three ways to discover

- **Catalog browser.** Browse the catalog UI to see available categories, actions, and the
  providers serving each route, with example calls.
- **CLI search.** Search the catalog from the command line to find routes by keyword or
  category — useful for both humans and agent tooling.
- **Catalog API.** Query the catalog programmatically so an agent can enumerate available
  routes and their prices at runtime and decide what to call.

## What a route tells you

For each route the catalog exposes the information a caller needs before paying:

- The **task** (`category/action`) and the **provider** fulfilling it.
- The **price** (provider price plus h402 fee, in Base USDC).
- The **input/output shape** and an example call.
- Whether the route is **free** or **paid**.

## Route addressing

Routes are called through a stable proxy path:

```
/api/proxy/{category}/{action}/{provider}
```

so a caller can target a specific provider for a task, or rely on the catalog to choose
one. Once you know the route, paying for it follows the flow in
[How Paying Works](how-paying-works.md); see [Call & Pay](call-and-pay.md) for concrete
CLI and HTTP examples.

> **TODO (operator):** link the live catalog browser and catalog API endpoint here once the
> production domain is confirmed.
