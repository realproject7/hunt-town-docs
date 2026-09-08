# For Builders

The other side of the market is the **API builders** who supply capabilities. h402 gives an
existing API a path to agent demand without building billing, key management, or a customer
relationship for every caller.

## What you get

- **Per-call monetization.** Your service is paid per call in Base USDC. No per-customer
  billing, no API keys to issue, no invoicing.
- **Agent-reachable distribution.** Once listed, your capability is discoverable by every
  agent that has mounted h402 — found by the task it performs, not by your brand.
- **You don't need to speak x402 first.** h402 sits in front as the paid proxy: it presents
  the challenge, settles the caller's payment, calls your upstream, and wraps the result.

## How a listing works

1. **Expose an endpoint.** One capability, one price, reachable over HTTP on Base.
2. **h402 lists it as a provider candidate** for the matching `category/action`, with your
   native input schema and an example.
3. **It is paid-probed.** A real, paid call is made against your live endpoint and the exact
   response is stored as your sample. Only then does the provider go **enabled** — see
   [Providers & Verification](providers.md).
4. **It is scored on live traffic.** Success rate and latency feed a quality score that
   ranks enabled providers.
5. **You compete on quality-adjusted price.** Out-score your peers and your provider becomes
   the catalog's recommended default for that capability.

## How you get paid

Callers pay h402's treasury; h402 pays you from its operating wallet after the call
settles. Your price is what you set — the caller's quote is your price plus h402's 5%
markup, shown transparently before they authorize.

## Getting listed today

Listing is currently **reviewed by the h402 team** rather than self-serve. Submissions go
through the Builders page on the h402 site, and the team runs the paid evaluation before a
capability appears in the catalog.

Self-serve onboarding with automatic evaluation is planned but **not yet available** — do
not assume a builder dashboard exists today.

> **TODO (operator):** add the live Builders page link and the current submission form URL
> once the production domain is confirmed, and update this page when self-serve onboarding
> ships.
