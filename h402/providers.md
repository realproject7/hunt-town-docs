# Providers & Verification

A **capability** is a task. A **provider** is one concrete implementation of it. Most of
what makes h402 a market rather than a directory lives here: how providers are verified, and
who decides which one serves a call.

## Selection is explicit

**Every executable call is pinned to one provider.**

```
GET|POST /routes/{provider}/{category}/{action}
```

The caller — a human, an agent, or the CLI on the agent's behalf — chooses the provider
before the call. There is no request-time routing and no automatic failover to a different
provider mid-call.

> **The automatic router is retired.** An earlier version of h402 accepted
> `/routes/auto/...` and picked a provider server-side. That path now returns **`410 Gone`**
> with recovery metadata — the current providers, their statuses, and each one's pinned
> path — and never quotes or charges. If you are working from older material that describes
> automatic routing, it no longer applies.

### The recommended default

The catalog publishes a `defaultProvider` for each capability. It is a **display
recommendation**, computed from live health and quality-adjusted price over a minimum
sample threshold — not a router. A client may pin it as a convenience (the CLI does exactly
this when `--provider` is omitted: it reads the recommendation, then pins it), but the
choice is still made by the client, before the call, and is reported back in the response so
the decision is auditable.

## Verification is binary, and it is earned by paying

There is no verification score. A provider is either **enabled** or it is not, and *enabled
is the verification signal*:

- A provider becomes enabled only after a **real, paid probe** against its live endpoint —
  never from documentation, a mock, or an assumed response shape.
- The **exact response body** from that paid call is stored as the provider's **sample**.
  This is what the catalog shows you as a "real sample".
- If a probe fails, it **never overwrites existing evidence**. The provider is disabled with
  a curation note instead. Nothing is left enabled without evidence behind it.

This is why the catalog can claim that every listed provider has been paid-tested: listing
requires it.

## Quality score is a different thing

Separately from verification, each enabled provider carries a continuous **quality score**
derived from live call success rate and latency. It is used for **one purpose**: ranking
enabled providers so the catalog can recommend a default.

Do not read it as a trust or safety rating. Verification is the binary gate; quality score
is a ranking signal among providers that already passed it.

## What this means when you choose

For a given capability you can compare, side by side:

- **price** per call,
- the **stored real sample** — the actual shape and quality of what you will get back,
- the provider's **native input schema**, and
- whether it is currently enabled.

Then you pin one. See [Call & Pay](call-and-pay.md).
