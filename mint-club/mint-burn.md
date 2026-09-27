# Mint & Burn

Trading a Mint Club asset means **minting** (buying) or **burning** (selling) against its
bonding curve. There is no order book and no liquidity pool. Every trade is with the curve
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

A holder can always burn back to the curve rather than wait for a buyer.

## For holders

Minting and burning are always open at a quotable price, backed by the reserve held in the
curve. See [Bonding Curves](bonding-curves.md). On rising curves (linear or exponential),
earlier minters buy at lower points on the curve.

> A creator royalty can apply to each mint and burn, and it is taken as part of the trade.
> The protocol's share comes out of that royalty when the creator claims it. See
> [Economics](economics.md).
