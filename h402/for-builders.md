# For Builders

The other side of h402 is the **builders and providers** who supply capabilities. If you
operate an API or a service, h402 lets you expose it as a **paid route** that any caller —
human app or autonomous agent — can discover and pay for per call, settled in stablecoins.

## What you get

- **Per-call monetization.** Your service is callable as a `category/action` route and is
  paid for each call in Base USDC — no per-customer billing relationships, no API-key
  management, no invoicing.
- **Agent-reachable distribution.** Once your route is in the catalog, it is discoverable by
  every agent and app on h402, addressed by task rather than by your brand or SDK.
- **Forwarded settlement.** Caller payments settle on Base; provider payouts are forwarded
  from the configured Base operating wallet, separate from the user treasury that receives
  caller payments.

## How routes are served

A route is addressed at:

```
/api/proxy/{category}/{action}/{provider}
```

h402 sits in front as a paid proxy: it presents the `402` quote to the caller, settles the
payment, forwards the call to your upstream service, and wraps the result in the standard
[response envelope](call-and-pay.md). Pricing is your provider price plus the h402 fee
(a basis-point markup), surfaced transparently in the quote.

## Listing in the catalog

Routes live in a curated **catalog** organized by category and action, each with an example
call and price. Getting listed means your capability becomes part of the task-first index
that callers and agents search and browse — see [Discover Routes](discover-routes.md).

> **TODO (operator):** document the provider onboarding path — how a builder submits a
> route, sets pricing, configures the upstream, and gets listed in the catalog — with the
> real Builders section link once published.
