# Bonding Curves

A **bonding curve** is the heart of Mint Club. It is a smart contract that defines the price
of a token as a function of its supply: as more is minted, the price moves along the curve;
as supply is burned, it moves back. The curve **is** the market — there is no external
liquidity pool to seed.

## How a curve works

- Every asset is backed by a **reserve** of a chosen reserve token, held in the curve.
- **Minting (buying)** deposits reserve and issues new supply at the current curve price.
- **Burning (selling)** removes supply and returns reserve at the current curve price.
- Price is **deterministic**: it depends only on where you are on the curve, so there is
  always a quotable mint/burn price and instant liquidity.

## Curve types

Mint Club lets creators choose the **shape** of the curve and the price-variation intervals,
so the asset's economics match the intent:

| Curve | Behavior | Suits |
| --- | --- | --- |
| **Linear** | Price rises steadily with supply. | Predictable, fair-launch-style economics. |
| **Exponential** | Price accelerates as supply grows. | Early-supporter upside, scarcity plays. |
| **Flat** | Price stays constant. | Fixed-price mints, memberships, stable units. |

Creators can also tune the **price-variation intervals** — how the price steps along the
curve — to shape the experience between these extremes.

## Reserve backing and refunds

Because the reserve is held in the curve, the model is **reserve-backed and refundable**: a
holder can always burn back to the curve and reclaim reserve at the current price. This is
the property that makes Mint Club assets fundamentally different from purely speculative
tokens — there is real reserve behind the supply, redeemable at any time through the curve.

In the Hunt Town economy, the reserve token is frequently **HUNT**, which is how Co-op
project tokens and Building NFTs become [HUNT-backed](../hunt/reserve-token.md).
