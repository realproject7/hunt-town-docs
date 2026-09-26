# HUNT as the Reserve Token

HUNT is more than the ecosystem's unit of account. It is its **reserve**. This page explains
what "reserve token" means mechanically and why it makes the factory's products reinforce
each other instead of competing for the same liquidity.

> This is the **structural** half of HUNT's role: HUNT sitting underneath the tokens the
> factory launches. The **economic** half, product revenue buying HUNT to back the Factory
> NFT, is covered in [Factory NFT](../factory-nft/overview.md).

## The mechanism

Project tokens in the Co-op and tokens created on Mint Club's HUNT-backed curves are minted
against a **bonding-curve reserve**. When someone buys one of these tokens, HUNT flows
**into** that token's reserve and stays **locked** there while those tokens are held. When
they sell, HUNT flows back out.

The [Factory NFT](../factory-nft/overview.md) holds HUNT too, on Ethereum. That HUNT is held
by the Factory NFT contract rather than a curve reserve: Factory NFTs mint at NAV and burn
for 95% of NAV, with no curve.

Because HUNT has **no inflationary emission**, the only way new assets enter the economy is
by locking existing HUNT. So:

- More projects launched → more HUNT locked in reserves.
- More Factory NFTs minted → more HUNT held by the Factory NFT contract.
- More activity across the ecosystem → **less circulating HUNT**, concentrated backing
  behind everything that has been issued.

## Why it matters

Most onchain projects launch a fresh token and compete with every other token for
attention and liquidity. The reserve model does the opposite: it **links** projects.

- **A shared foundation.** Each builder runs an independent project, but every project is
  backed by the same reserve. When one project grows, it locks more HUNT behind the whole
  economy, not behind a token of its own.
- **Growth locks HUNT.** Growth tightens supply. Reserves hold more HUNT as activity grows,
  and circulating HUNT falls.
- **HUNT behind every token.** Curve assets are reserve-backed rather than purely
  speculative: there is HUNT actually held behind them, redeemable through the curve.

This is the core of Hunt Town's thesis: a shared economy where **the success of one
project contributes to the strength of all of them**, rather than fragmenting a community
across disconnected tokens.

## Relationship to product tokens

- **Co-op project tokens** are HUNT-backed child tokens. See
  [HUNT-backed Project Tokens](../co-op/hunt-backed-project-tokens.md).
- **The Factory NFT** holds HUNT behind every NFT. See
  [Factory NFT](../factory-nft/overview.md).
- **Mint Club** provides the bonding-curve engine that makes reserve-backing possible. See
  [Mint Club Overview](../mint-club/overview.md).
