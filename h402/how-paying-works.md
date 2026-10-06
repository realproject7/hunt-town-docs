# How Paying Works

h402 turns the HTTP `402 Payment Required` status into a real payment handshake, built on
the **x402 v2** standard. The exchange is non-custodial: the caller's key signs locally and
never leaves their machine.

## The handshake

1. **Call.** A normal request to the pinned provider. Free capabilities, and calls covered
   by credit, return immediately, with no payment step.
2. **Challenge.** If payment is required, the server returns `402` with the exact amount,
   the payee, and a short validity window.
3. **Sign.** The caller signs **an EIP-3009 authorization** over **Base USDC** for exactly
   the quoted amount. No funds move yet and no key is shared.
4. **Settle.** The caller retries with the signature attached. The authorization settles
   into h402's treasury through the Coinbase CDP facilitator, the provider call executes,
   and the result returns.

## Where the money goes

Two hops, deliberately separated:

- The **caller's** payment settles into h402's treasury.
- h402 then pays the **upstream provider** from its own operating wallet: over x402 in Base
  USDC where the provider supports it, otherwise in the way that provider accepts.

The caller therefore signs one authorization, in one asset, on one chain, regardless of how
the provider behind the capability prefers to be paid.

## Pricing and fees

A quoted price is the **provider's price plus h402's markup of 5%**. The markup is included
in the quote, so the caller authorizes the final amount and there is nothing added
afterwards.

Prices are denominated in USDC, which is what lets an agent reason about spend in dollars.
Every payment is a one-shot, exact charge.

## Credits

Callers can hold **bonus credits**, issued today as onboarding grants, which are drawn down
before any USDC is charged.

## Properties that matter for agents

- **Bounded authorizations.** Each signature covers a single quoted amount and expires
  quickly, so a stale one cannot be replayed for more than it authorized.
- **No ambiguous charges.** A request whose payment state is unclear is not forwarded;
  it is reconciled rather than retried against another provider.
- **No double charges.** A retried call is not charged twice, and the client refuses a new
  price challenge on a retry instead of paying again.
