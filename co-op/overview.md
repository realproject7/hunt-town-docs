# Co-op — Overview

**Co-op is a HUNT-backed launchpad and DEX.** Builders launch project tokens backed by HUNT,
and anyone can buy or sell those tokens against HUNT on their bonding curves. It is the
product the renewed hunt.town grew out of: for years "Hunt Town" and the Co-op were the same
thing. Today the Co-op is one product in the studio, and the most direct expression of the
[reserve-token](../hunt/reserve-token.md) thesis.

## The idea

Most launchpads spin up isolated projects that compete for the same liquidity. The Co-op
does the opposite: it **connects every project through a common reserve asset, HUNT**.

- **Builders launch** project tokens backed by HUNT. Each token has a market from the first
  block, with no liquidity pool to seed.
- **Anyone trades** those tokens against HUNT. Buying a token locks HUNT in its reserve, and
  selling returns HUNT from it.
- As projects grow, **more HUNT locks** into their bonding-curve reserves, which expands the
  Co-op's total value locked and tightens HUNT's circulating supply.

## Co-op structure

```
   Builders ──launch──▶  HUNT-backed project tokens  ◀──buy / sell──  Anyone
                                  │
                   every reserve is held in HUNT
```

Each builder runs a completely independent project, yet every project shares the same
reserve asset: the success of one strengthens the foundation of HUNT, and by extension every
other token built on it.

## In this section

- [Launchpad & DEX](launchpad-and-dex.md): how launching and trading work together.
- [Launch a Project Token](launch-a-project-token.md): how builders launch.
- [HUNT-backed Project Tokens](hunt-backed-project-tokens.md): the token model.

> Co-op is moving to its own domain, **coop.hunt.town**, as the renewed hunt.town becomes
> the studio landing page.
