# h402 — Overview

**h402 is task-first onchain payments for the agent economy.** It lets an application — or
an autonomous AI agent — discover a capability, pay for it per call, and get the result,
with settlement in stablecoins and **no custodial account, no API-key billing, and no
human in the loop**.

It is Hunt Town's product for the "Agent" half of the
[Builder & Agent Economy](../hunt-town/builder-agent-economy.md): the payments layer that
software needs once it starts doing real economic work on its own.

## The problem

Agents can already call APIs, generate media, run research, and complete tasks. What they
cannot easily do is **pay for those services autonomously**. Traditional payment rails
assume a human with a credit card, an account, and a billing relationship per provider.
That does not scale to an agent that needs to call dozens of services, once each, at
machine speed.

## The approach

h402 builds on the **x402** standard — the HTTP `402 Payment Required` status code, used as
a real payment handshake. A caller requests a capability; if payment is required, the
server responds with a signed price quote; the caller authorizes a stablecoin payment
locally and retries; the call settles and returns the result.

Three things make it suited to agents:

- **Task-first, not provider-first.** You ask for what you want done — `category/action`,
  e.g. `ai/image-generate` — and h402 routes it to a provider. You discover capabilities by
  task, not by integrating each vendor.
- **Per-call, non-custodial settlement.** Payment is a signed authorization (EIP-3009) over
  **Base USDC**. Keys never leave the caller; there is no account to top up or balance to
  custody.
- **Stablecoin-denominated.** Prices and settlement are in USDC, so costs are predictable
  and agents reason about spend in dollars.

## How the pieces fit

| Concept | What it is |
| --- | --- |
| **Route** | A callable capability, named `category/action` and served via a provider. |
| **Catalog** | The discoverable index of routes — browse, search, or query it. |
| **Quote** | A signed `402` response stating the price for a call. |
| **Authorization** | An EIP-3009 signature over Base USDC that settles the call. |
| **Envelope** | The structured response wrapping provider data plus routing metadata. |

The rest of this section walks through each: [How Paying Works](how-paying-works.md),
[Discover Routes](discover-routes.md), [Call & Pay](call-and-pay.md),
[For AI Agents](for-ai-agents.md), [For Builders](for-builders.md), and the
[@h402/core SDK](h402-core-sdk.md).

> **TODO (operator):** confirm the production domain at launch (currently
> `h402-test.hunt.town`, docs at `h402-test.hunt.town/docs`; intended
> `h402.hunt.town`) and update links throughout this section.
