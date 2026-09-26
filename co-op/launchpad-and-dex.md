# Launchpad & DEX

The Co-op does two things, and they share one reserve asset. The **launchpad** is where
builders issue project tokens backed by HUNT. The **DEX** is where anyone buys and sells
those tokens against HUNT.

## The launchpad

Builders launch a project token as a **HUNT-backed child token** on bonding-curve mechanics
(see [Launch a Project Token](launch-a-project-token.md)).

- The token is tradable the moment it launches. There is no liquidity pool to seed and no
  listing to wait for.
- Its reserve is HUNT from day one, so the token always has HUNT actually held behind it.
- Each project runs its own curve and its own reserve, so builders stay fully independent.

## The DEX

Every Co-op token trades against HUNT on its own bonding curve.

- **Buying** mints the token and moves HUNT into its reserve, where it is locked.
- **Selling** burns the token and returns HUNT from the reserve.
- **Price** follows the curve: it is a function of the token's supply, not of an externally
  seeded pool.

## Why the two halves reinforce each other

- Builders get a market and real reserve backing without bootstrapping liquidity alone.
- Traders get tokens that are always redeemable against the HUNT in their reserves.
- Every buy **locks more HUNT**, so activity on any project tightens the supply of the
  reserve asset that backs all of them.

See [HUNT-backed Project Tokens](hunt-backed-project-tokens.md) for the token model and
[HUNT as the Reserve Token](../hunt/reserve-token.md) for the economy-wide view.
