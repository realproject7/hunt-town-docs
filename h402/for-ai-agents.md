# For AI Agents

h402 is designed so an **autonomous agent** can pay for capabilities on its own. There is
no account to register, no API key to manage per provider, and no human approval in the
payment loop — just a funded wallet and the ability to sign locally.

## Three-step setup

1. **Install the CLI.** Add the h402 CLI to the agent's environment so it can discover and
   call routes.
2. **Create and fund a wallet.** Generate a wallet and fund it with **Base USDC**. This is
   the agent's spending account; h402 never custodies it.
3. **Call tasks.** Point the agent at a task (`category/action`) and let the CLI handle the
   `402` handshake — quote, local signature, retry, result.

Once set up, the agent calls capabilities the same way it would call any tool, and payment
happens transparently underneath.

## Why this fits agents

- **No human in the loop.** The agent signs its own EIP-3009 authorizations; there is no
  checkout, no card, no per-provider onboarding.
- **Task-first calling.** The agent reasons in terms of outcomes (`ai/image-generate`,
  `web/search`, `research/web-task`) and h402 routes to a provider — so adding a new
  capability does not mean integrating a new vendor SDK.
- **Predictable spend.** Prices are quoted in USDC before the agent commits, so it can
  budget and cap spend in dollars.
- **Safe retries.** Idempotency keys mean a retried call is not double-charged, which
  matters for agents running unattended on imperfect networks.

## Working from a framework

Agents built on common frameworks can drive h402 either through the CLI or directly through
the [@h402/core SDK](h402-core-sdk.md) for custom integrations (multiple signer backends —
viem, ethers, OWS — without the CLI wrapper).

> A proposed extension would let agents be funded by **Building NFT credits**: a Building
> holder could delegate a weekly stablecoin h402 credit to an agent's wallet, so the agent
> pays from that allowance before drawing on its own USDC. See
> [Building NFTs → h402 credits](../hunt/building-nfts.md) (under review).

> **TODO (operator):** add the exact install command, an end-to-end example agent
> (e.g. Claude) calling a paid route, and the funding instructions once finalized.
