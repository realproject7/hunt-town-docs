# @h402/core SDK

`@h402/core` is the npm library for integrating h402 **without the CLI**. It is for builders
who want to drive the payment flow directly from their own application or agent code.

## What it does

`@h402/core` implements the client side of the [payment handshake](how-paying-works.md):

- issue a request to a route,
- receive and parse the `402` quote,
- produce the EIP-3009 authorization over Base USDC with a signer you provide,
- retry with the `PAYMENT-SIGNATURE`, and
- return the parsed [response envelope](call-and-pay.md).

## Pluggable signers

The library does not assume a particular wallet stack. It supports **multiple signer
backends**, so you can wire it to whatever your app or agent already uses:

- **viem**
- **ethers**
- **OWS**

Because the signer is supplied by you and runs in your environment, settlement stays
**non-custodial** — exactly as with the CLI, the private key never leaves your process.

## When to use the SDK vs the CLI

| Use the CLI | Use `@h402/core` |
| --- | --- |
| Quick start, scripts, agent tool-calls | Custom app/agent integration |
| You want the flow handled for you | You want control over signing and transport |
| One-off or interactive calls | Programmatic, high-volume, embedded calls |

> **TODO (operator):** add the package install command, the minimal `viem` and `ethers`
> usage snippets, and a link to the package README once the API surface is frozen for
> launch.
