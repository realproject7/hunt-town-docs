# Mint & Burn

Trading a Mint Club asset means **minting** (buying) or **burning** (selling) against its
bonding curve. There is no order book and no liquidity pool — every trade is with the curve
itself, at a deterministic price.

## Minting (buy)

To acquire an asset, you **mint** it:

- You deposit the **reserve token** into the curve.
- New supply is **issued to you** at the current curve price.
- The deposit is added to the reserve, and the price moves **up** along the curve for the
  next minter.

Because the curve always has a price, minting is instant and needs no counterparty.

## Burning (sell)

To exit, you **burn** the asset:

- Your supply is **removed** (burned).
- **Reserve is returned to you** at the current curve price.
- The price moves **down** along the curve for the next trade.

This is the redeemable, refundable property of the model: a holder can always burn back to
the curve and reclaim reserve, rather than depending on finding a buyer.

## Benefits for holders

- **Instant liquidity, both ways.** You can always mint or burn at a quotable price.
- **Reserve-backed value.** There is real reserve held behind the supply, redeemable through
  the curve.
- **Transparent pricing.** Price is a deterministic function of supply, not a thin or
  manipulable order book.
- **Early-supporter upside.** On rising curves (linear/exponential), earlier minters acquire
  at lower points on the curve.

> Fees apply on mint/burn — see [Economics](economics.md) for creator royalties and platform
> fees, which are taken as part of the trade.
