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
h402 auth                       # sign in with your wallet
h402 credits                    # show credit balance
h402 search <query>             # find capabilities
h402 show <category/action>     # inspect a capability and its providers
h402 quote <category/action>    # price a call without paying
h402 call <category/action>     # call and pay
```

Wallets are generated and stored locally, optionally passphrase-protected. `H402_API_URL`
overrides the backend origin; `H402_WALLET_PASSPHRASE` applies to wallets that opted into
one.

## `@h402/core`

Use `@h402/core` when you want the payment flow inside your own application or agent rather
than shelling out to the CLI. It implements the client half of the
[handshake](how-paying-works.md):

- parse the `402` challenge,
- build the EIP-3009 authorization over Base USDC with **a signer you supply**,
- encode the payment headers for the retry.

Because the signer runs in your process, settlement stays **non-custodial** exactly as it is
with the CLI — the private key never leaves your environment.

## Which to use

| Use the CLI | Use `@h402/core` |
| --- | --- |
| Agents that mounted the skill | Custom app or agent integration |
| Scripts, one-off and interactive calls | Programmatic, high-volume, embedded calls |
| You want the flow handled for you | You want control over signing and transport |

> Both packages are pre-1.0; the API surface may still change before launch.
