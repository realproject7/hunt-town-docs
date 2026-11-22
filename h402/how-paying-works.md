# How Paying Works

h402 uses the **x402** standard, which turns the HTTP `402 Payment Required` status into a
payment handshake. The caller's key signs locally and never leaves their machine.

## The handshake

1. **Call.** A normal request to the pinned provider. Free capabilities, and calls covered by
   credits, return right away.
2. **Challenge.** If payment is required, the server returns `402` with the exact amount, the
   payee, and a short validity window.
3. **Sign.** The caller signs an authorization (EIP-3009) over **Base USDC** for exactly the
   quoted amount. No funds move yet.
4. **Settle.** The caller retries with the signature. h402 calls the provider, and the
   payment settles only if the provider returns a successful response. A failed call is not
   charged.

## Pricing

A quote is the provider's price plus h402's fee, in USDC. The caller sees the final amount
before signing, and nothing is added afterwards. Callers always pay in Base USDC, however the
provider behind the capability is paid.

## What callers can rely on

- **Bounded authorizations.** Each signature covers one quoted amount and expires quickly, so
  it cannot be reused for more.
- **No double charges.** A retried call is not charged twice, and the client refuses a new
  price challenge on a retry.
- **No unclear charges.** A request whose payment state is unclear is reconciled, not sent to
  another provider.
- **Credits come back.** Credits used on a failed call are returned.
