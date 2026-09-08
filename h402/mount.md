# Mount Once

The premise of h402 is that an agent should gain a market of capabilities from **one**
setup step, not one per API. That step is called **mounting**.

## What mounting actually is

Mounting is not a plugin registry or a package you register with h402. It is simpler: you
point your agent at h402's **skill file**, and the agent follows it.

```
claude "Read https://raw.githubusercontent.com/Steemhunt/h402-cli/main/SKILL.md
        and use it to <your task>"
```

The skill file teaches the agent the whole workflow — how to search the catalog, inspect a
capability, pick a provider, and pay for a call. From then on the agent can reach every
capability in the catalog without further setup.

## Supported clients

The same pattern works across the CLI-driven coding agents, swapping the binary:

| Client | Command |
| --- | --- |
| Claude | `claude` |
| Codex | `codex` |
| Cursor | `cursor-agent` |
| Gemini | `gemini` |

## What the agent does next

Following the skill file, the agent bootstraps itself:

1. **Install the CLI** — `npm i -g @h402/cli`
2. **Create a wallet** — `h402 wallet create --name agent`. The key is generated and stored
   locally; h402 never holds it.
3. **Fund it with Base USDC** — this is the agent's spending account.
4. **Call capabilities** — `h402 call <category/action> ...`

From there, paying for a capability is a normal tool call: the CLI handles the `402`
handshake, signs locally, and returns the result. See [Call & Pay](call-and-pay.md).

## Why this suits agents

- **No per-provider onboarding.** No accounts to create, no API keys to store or rotate, no
  vendor SDKs to install.
- **No human in the payment loop.** The agent signs its own authorizations; there is no
  checkout page and no card.
- **Spend is legible in dollars.** Prices are quoted in USDC before the agent commits, and
  `--max-usd` caps what a single call may spend.
- **Safe retries.** Idempotency keys mean a retried call is not charged twice.

> A proposed extension would let **Building NFT** holders delegate a recurring stablecoin
> h402 credit to an agent's wallet, so the agent spends that allowance before its own USDC.
> See [Building NFTs → h402 credits](../hunt/building-nfts.md) (under review).
