# Co-op: Overview

**Co-op is a HUNT-based launchpad and DEX at [coop.hunt.town](https://coop.hunt.town).**
Builders launch project tokens backed by HUNT, and anyone can buy or sell those tokens
against HUNT on their bonding curves. For years "Hunt Town" and the Co-op were the same
thing. Today the Co-op is one product of the factory, and the most direct expression of the
[reserve-token](../hunt/reserve-token.md) thesis.

## How it works

```
   Builders ──launch──▶  HUNT-backed project tokens  ◀──buy / sell──  Anyone
                                  │
                   every reserve is held in HUNT
```

- **Launch.** A builder launches a project token on its own bonding curve, with HUNT as the
  reserve from day one. It trades from the moment it launches, with no liquidity pool to
  seed and no listing to wait for. See [Launch a Project Token](launch-a-project-token.md).
- **Trade.** Anyone buys or sells the token against HUNT. Buying mints the token and locks
  HUNT in its reserve. Selling burns it and returns HUNT from the reserve, so a holder can
  always sell back to the curve. The price follows the curve as a function of supply, not
  an externally seeded pool.
- **One reserve.** Each project runs its own curve and reserve, so builders stay fully
  independent. Every reserve is HUNT, so each buy on any project locks more of the asset
  that backs all of them. See [HUNT-backed Project Tokens](hunt-backed-project-tokens.md).
