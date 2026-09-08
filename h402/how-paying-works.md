# How Paying Works

h402 turns the HTTP `402 Payment Required` status into a real payment handshake, built on
the **x402 v2** standard. The exchange is non-custodial: the caller's key signs locally and
never leaves their machine.

## The handshake

```
caller ──▶ call pinned provider   (idempotency-key, no payment)
caller ◀── 402  price challenge   (amount in Base USDC, payee, expiry)
caller ──▶ retry + signature      (EIP-3009 authorization, same idempotency key)
caller ◀── result                 (settlement confirmed)
```

1. **Call.** A normal request to the provider's pinned path. Free capabilities — and calls
   covered by credit — return immediately, with no payment step.
2. **Challenge.** If payment is required, the server returns `402` with the exact amount,
   the payee, and a short validity window.
3. **Sign.** The caller signs an **EIP-3009 `TransferWithAuthorization`** over **Base USDC**
   for exactly the quoted amount. No funds move yet and no key is shared.
4. **Settle.** The caller retries with the signature attached. The authorization is settled
   through an x402 facilitator, the provider call executes, and the result returns.

## Where the money goes

Two hops, deliberately separated:

- The **caller's** payment settles into h402's treasury.
- h402 then pays the **upstream provider** from its own operating wallet — over x402 on
  Base where the provider supports it, or via a one-shot charge for providers on other
  supported rails.

The caller therefore signs one authorization, in one asset, on one chain, regardless of how
the provider behind the capability prefers to be paid.

## Pricing and fees

A quoted price is the **provider's price plus h402's markup of 5%**. The markup is included
in the quote, so the caller authorizes the final amount and there is nothing added
afterwards.

Prices are denominated in USDC, which is what lets an agent reason about spend in dollars
and cap it with `--max-usd`.

## Credits

Callers can hold **credits** that are drawn down before any USDC is charged.

- `h402 auth` establishes a session by signing a challenge with your wallet — no password,
  no account.
- `h402 credits` shows the balance.
- Credits are consumed **earliest-expiring first**, and a call falls through to USDC once
  they are exhausted. `--no-credit` skips them entirely.

Today credits are issued as onboarding grants. The same mechanism is what a recurring
program — such as the proposed
[Building NFT credits](../hunt/building-nfts.md) — would run on.

## Properties that matter for agents

- **Non-custodial.** Signatures are produced client-side; h402 holds no user keys and no
  user balance.
- **Bounded authorizations.** Each signature covers a single quoted amount and expires
  quickly, so a stale one cannot be replayed for more than it authorized.
- **No ambiguous charges.** A request whose payment state is unclear is not forwarded;
  it is reconciled rather than retried against another provider.
- **Idempotent retries.** See [Call & Pay](call-and-pay.md).

> h402 is pre-1.0 and the payments layer is still evolving. Treat rail-level specifics here
> as current-as-documented rather than frozen.
