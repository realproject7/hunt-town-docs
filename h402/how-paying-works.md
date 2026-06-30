# How Paying Works

h402 turns the HTTP `402 Payment Required` status into a real, three-phase payment
handshake built on the **x402 v2** standard. The whole exchange is non-custodial: the
caller's wallet key signs locally and never leaves their machine.

## The three phases

### 1. Request

The caller makes a normal request to a route (`category/action`). If the route is free, it
returns immediately. If it requires payment, the server responds with **`402 Payment
Required`** and a **signed price quote** — the standard x402 `PAYMENT-REQUIRED` header —
stating the amount (in Base USDC), the payee, and the validity window for the
authorization.

### 2. Sign

The caller reviews the quote and, if acceptable, **signs a payment authorization locally**.
h402 uses **EIP-3009** (`transferWithAuthorization`) over Base USDC, so the signature
authorizes exactly the quoted amount to the quoted payee, valid only within a short timeout
window. No funds move yet, and no private key is shared with the server.

### 3. Settle

The caller retries the request, this time attaching the signature as the x402
`PAYMENT-SIGNATURE` header. The facilitator settles the authorized USDC payment on Base,
the provider call is executed, and the result returns alongside a `PAYMENT-RESPONSE`
header confirming settlement.

```
caller ──▶ request route
caller ◀── 402 PAYMENT-REQUIRED  (signed quote: amount, payee, expiry)
caller ──▶ retry + PAYMENT-SIGNATURE (EIP-3009 auth over Base USDC)
caller ◀── result + PAYMENT-RESPONSE (settlement confirmed)
```

## Properties that matter for agents

- **Non-custodial.** The signature is generated client-side; keys never leave the caller.
  There is no account to fund or balance to hold with h402.
- **Bounded authorizations.** Each authorization is for a single quoted amount and expires
  after a short window (on the order of a couple of minutes), so a leaked or stale
  signature cannot be replayed for more than it authorized.
- **Idempotency.** Calls carry an **idempotency key** so a retried request is de-duplicated
  — an agent that retries on a flaky network is not charged twice for one task.
- **Settlement.** Payments settle on **Base USDC** via the facilitator; provider payouts are
  forwarded from the configured Base operating wallet.

## Pricing

A route's price is the provider's price plus h402's fee. The fee is a fixed markup applied
on top of the provider price (basis-point markup, e.g. 5%), surfaced transparently in the
quote so the caller authorizes the full, final amount and there are no hidden charges.

> Credits (see [Building NFTs → h402 credits](../hunt/building-nfts.md)) — a proposed
> mechanic — would be drawn down against the quoted amount **before** any USDC is charged,
> via the `h402-credit` x402 extension.
