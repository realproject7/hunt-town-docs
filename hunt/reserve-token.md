# HUNT as the Reserve Token

HUNT is more than the ecosystem's unit of account — it is its **reserve**. This page
explains what "reserve token" means mechanically and why it makes the studio's products
reinforce each other instead of competing for the same liquidity.

> This is the **structural** half of HUNT's role: HUNT sitting underneath the tokens the
> studio launches. The **economic** half — product revenue funding buybacks and burns — is
> covered in [Buyback & Burn](buyback-and-burn.md).

## The mechanism

Every asset the ecosystem issues — project tokens in the Co-op, Building NFTs, and tokens
created on Mint Club's HUNT-backed curves — is minted against a **bonding-curve reserve**.
When someone mints one of these assets, HUNT flows **into** that asset's reserve and is
**locked** there for as long as the asset exists. When they burn/sell, HUNT flows back out.

Because HUNT has **no inflationary emission**, the only way new assets enter the economy is
by locking existing HUNT. So:

- More projects launched → more HUNT locked in reserves.
- More Buildings minted → more HUNT locked in reserves.
- More activity across the ecosystem → **less circulating HUNT**, concentrated backing
  behind everything that has been issued.

## Why it matters

Most onchain projects launch a fresh token and compete with every other token for
attention and liquidity. The reserve model does the opposite: it **links** projects.

- **Shared upside.** Each builder runs an independent project, but every project is backed
  by the same reserve. When one project grows and locks more HUNT, it strengthens the
  foundation under HUNT itself — and by extension every other token and NFT in the economy.
- **Deflationary by construction.** Growth tightens supply. The reserve's total value
  locked rises with ecosystem activity, and circulating HUNT falls. Separately, revenue
  from the studio's products can fund [buybacks and burns](buyback-and-burn.md) that remove
  HUNT permanently.
- **A real floor.** Because assets are reserve-backed rather than purely speculative,
  there is HUNT actually held behind them, redeemable through the curve.

This is the core of Hunt Town's thesis: a shared economy where **the success of one
project contributes to the strength of all of them**, rather than fragmenting a community
across disconnected tokens.

## Relationship to product tokens

- **Co-op project tokens** are HUNT-backed child tokens — see
  [HUNT-backed Project Tokens](../co-op/hunt-backed-project-tokens.md).
- **Building NFTs** are HUNT-backed membership assets — see
  [Building NFTs](building-nfts.md).
- **Mint Club** provides the bonding-curve engine that makes reserve-backing possible —
  see [Mint Club Overview](../mint-club/overview.md).
