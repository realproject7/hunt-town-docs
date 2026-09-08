# h402 — Overview

**h402 is the Agent Capability Market Layer — the x402 capability store for agents.**
Mount it once, and an agent can discover, inspect, and pay for a whole market of
capabilities: web research, onchain data, AI generation, maps, finance, security checks and
more, without setting up each API separately.

It is Hunt Town's product for the "Agent" half of the
[Builder & Agent Economy](../hunt-town/builder-agent-economy.md).

## The problem

An agent that needs ten different services today needs ten integrations: ten sets of API
keys, ten billing relationships, ten response shapes, ten SDKs. Every new capability is a
new procurement problem, and none of it is something an agent can do on its own at machine
speed.

h402 collapses that into **one integration and one payment rail**.

## Three ideas

- **Mount once.** The agent reads one skill file and gains the whole catalog. Adding a
  capability later means nothing new to install — see [Mount Once](mount.md).
- **Verified providers, explicit choice.** Every listed provider has been paid-tested with
  its real response stored as a sample. The caller compares samples and per-call prices and
  **pins** the provider it wants — see [Providers & Verification](providers.md).
- **Pay per call.** Paid capabilities settle in **Base USDC** over **x402**, signed locally
  by the caller's wallet. No per-provider API keys, no subscriptions, no custody — see
  [How Paying Works](how-paying-works.md).

## The vocabulary

These three nouns are used precisely throughout this section.

| Term | What it is |
| --- | --- |
| **Capability** | One task, named `category/action` — e.g. `web/search`. It describes the outcome, not the vendor. |
| **Provider** | One concrete implementation of a capability, with its own input schema, price, upstream service, and a stored real-response sample. A capability can have many providers. |
| **Call** | One request against **one pinned provider** of a capability. Every executable call names its provider explicitly. |
| **Catalog** | The curated index of capabilities and their providers, browsable by humans and queryable by agents. |

Capabilities are organised into categories such as `ai`, `web`, `crypto`, `finance`,
`maps`, `research`, `security`, `social`, `travel`, and `weather`.

> **Provider selection is explicit.** Earlier versions of h402 offered an automatic router
> that picked a provider at request time. That has been **retired** — the catalog publishes
> a recommended default, but the caller decides. See
> [Providers & Verification](providers.md).

## Two sides of the market

- **For agents and apps** — mount the skill, search the catalog, call what you need, pay per
  call. Start at [Mount Once](mount.md).
- **For API builders** — list a capability and reach agent demand without building billing.
  See [For Builders](for-builders.md).

## Where the pieces are documented

[Mount Once](mount.md) · [Discover Capabilities](discover-capabilities.md) ·
[Providers & Verification](providers.md) · [Call & Pay](call-and-pay.md) ·
[How Paying Works](how-paying-works.md) · [For Builders](for-builders.md) ·
[SDK & CLI Packages](packages.md).

> **TODO (operator):** h402 is **pre-launch**. The configured production origin is
> `h402.hunt.town`, which does not resolve yet; the accessible environment is
> `h402-test.hunt.town`. Confirm the launch domain and update every link in this section
> when it goes live.
