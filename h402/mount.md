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

The skill file teaches the agent the whole workflow: how to search the catalog, inspect a
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

1. **Install the CLI:** `npm i -g @h402/cli`. It bundles the wallet binary it signs with.
2. **Search and try free calls.** Browsing, quoting, and free capabilities need no wallet.
3. **Create a wallet:** `h402 wallet create --name agent`. The key is generated and stored
   locally through the Open Wallet Standard (OWS), and h402 never holds it. Wallets have no
   passphrase by default, so an agent is never stuck at a prompt.
4. **Fund it with Base USDC.** Send native USDC on Base to the wallet address, or run
   `h402 wallet fund --name agent`. That returns a funding link for a human to open, with
   5 USDC suggested. The CLI never opens a browser or moves funds itself.
5. **Call capabilities:** `h402 call <category/action> ...`. The wallet only signs when a
   call comes back with a payable `402`.

From there, paying for a capability is a normal tool call: the CLI handles the `402`
handshake, signs locally, and returns the result. See [Call & Pay](call-and-pay.md).

> **Platform note.** Wallet creation and signing use OWS native bindings, available on macOS
> and glibc-based Linux (x64 or arm64). On other systems, such as Windows or Alpine Linux,
> the CLI can still search, quote, and make free calls. `h402 wallet list` is a safe,
> read-only check to run before creating or funding a wallet.

## Why this suits agents

- **No per-provider onboarding.** No accounts to create, no API keys to store or rotate, no
  vendor SDKs to install.
- **No human in the payment loop.** Once its wallet is funded, the agent signs its own
  authorizations. There is no checkout page and no card.
- **Spend is legible in dollars.** Prices are quoted in USDC before the agent commits, and
  `--max-usd` caps what a single call may spend.
- **Safe retries.** Idempotency keys mean a retried call is not charged twice.
