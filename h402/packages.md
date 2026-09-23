# SDK & CLI Packages

Two packages are published for callers. Both are **open source (MIT) and on npm**; the h402
web application itself is a private repository.

| Package | What it is |
| --- | --- |
| **`@h402/cli`** | The command-line client — wallet, catalog search, quoting, and paying for calls. What agents use after [mounting](mount.md). |
| **`@h402/core`** | A dependency-light protocol toolkit: x402 types, header codecs, and the EIP-3009 typed-data builder. Signer-agnostic. |

## `@h402/cli`

```
npm i -g @h402/cli
```

Command surface:

```
h402 wallet create | list | restore | address | balance | fund
h402 auth                       # start a bonus-credit session with your wallet
h402 credits                    # show your bonus-credit balance
h402 search <query>             # find capabilities
h402 show <category/action>     # inspect a capability and its providers
h402 quote <category/action>    # price a call without paying
h402 call <category/action>     # call and pay
```

Wallets are created and stored locally through the Open Wallet Standard (OWS), with no
passphrase by default. `H402_WALLET_PASSPHRASE` applies only to wallets that opted into
one. Set `"defaultWallet"` in `~/.h402/config.json` to choose the wallet used when no
`--name` is given. If that wallet is missing, the CLI fails rather than use another one.

The CLI targets the production backend, `https://h402.hunt.town`, by default.
`H402_API_URL` or `--api-url` points it somewhere else, such as a local development server.

OWS signing relies on native bindings for macOS and glibc-based Linux, on x64 or arm64.
Elsewhere the CLI can still search, quote, and make free calls, but it cannot create wallets
or sign payments. `h402 wallet list` is a read-only check to run first.

## `@h402/core`

Use `@h402/core` when you want the payment flow inside your own application or agent rather
than shelling out to the CLI. It implements the client half of the
[handshake](how-paying-works.md):

- parse the `402` challenge,
- build the EIP-3009 authorization over Base USDC with **a signer you supply**, such as
  viem, ethers, or OWS,
- encode the payment headers for the retry.

Because the signer runs in your process, settlement stays **non-custodial** exactly as it is
with the CLI — the private key never leaves your environment. The CLI itself is built on
`@h402/core`.

## Which to use

| Use the CLI | Use `@h402/core` |
| --- | --- |
| Agents that mounted the skill | Custom app or agent integration |
| Scripts, one-off and interactive calls | Programmatic, high-volume, embedded calls |
| You want the flow handled for you | You want control over signing and transport |

> Both packages are pre-1.0, so the API surface may still change between releases.
