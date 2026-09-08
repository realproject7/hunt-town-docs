# Launch a Project Token

Builders join the Co-op by **launching a project token**. Every project in the Co-op issues
its token as a **HUNT-backed child token** using bonding-curve mechanics, so the token has a
real reserve behind it from day one and a market that backers can mint into immediately.

## What launching gives a builder

- **A market from day one.** The token is tradable on its bonding curve as soon as it
  launches — no need to seed a liquidity pool or list on a DEX first.
- **Daily demand.** Backers direct their [Daily BP](daily-backing-point.md) at projects they
  support, so a launched token receives recurring daily minting rather than a one-time launch
  spike.
- **HUNT backing.** The token is backed by HUNT in its bonding-curve reserve; as the token's
  activity grows, more HUNT locks into that reserve.

## How it works mechanically

A project token is a **HUNT-backed child token** on a bonding curve (powered by the
[Mint Club](../mint-club/overview.md) protocol that underpins much of the ecosystem):

1. The builder configures and launches the token.
2. Backers mint it — with BP or HUNT — moving HUNT into the token's reserve.
3. The price moves along the bonding curve as supply changes; selling/burning returns HUNT
   from the reserve.

Because each project runs on its own curve and its own reserve, builders run **completely
independent projects** while still being connected through the shared HUNT reserve — the
core of the [Co-op model](overview.md).

## Shared upside

Every project launched strengthens the whole: when a project token grows in market activity,
**more HUNT becomes locked** inside its bonding-curve pool. So even though each builder runs
an independent project, all of them share upside across the Co-op, and the success of one
reinforces the foundation under every other token and NFT in the economy.
