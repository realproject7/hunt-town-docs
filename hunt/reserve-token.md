# HUNT as the Reserve Token

HUNT is the **reserve** behind [Co-op](../co-op/overview.md) project tokens and other
HUNT-backed tokens on [Mint Club](../mint-club/overview.md).

## The mechanism

Project tokens in the Co-op and tokens created on Mint Club's HUNT-backed curves are minted
against a **bonding-curve reserve**. When someone buys one of these tokens, HUNT flows
**into** that token's reserve and stays **locked** there while those tokens are held. When
they sell, HUNT flows back out.

The [Factory NFT](../factory-nft/overview.md) holds HUNT too, on Ethereum. That HUNT is held
by the Factory NFT contract rather than a curve reserve: Factory NFTs mint at NAV and burn
for 95% of NAV, with no curve.

Because HUNT has **no inflationary emission**, the only way new HUNT-backed assets come into
existence is by locking existing HUNT. So:

- More projects launched → more HUNT locked in reserves.
- More Factory NFTs minted → more HUNT held by the Factory NFT contract.
- More activity across the ecosystem → **less circulating HUNT**, concentrated backing
  behind everything that has been issued.

## Why it matters

Most onchain projects launch a fresh token and compete with every other token for
attention and liquidity. The reserve model does the opposite: it **links** projects. Each
builder runs an independent project, but every project is backed by the same reserve. When
one project grows, it locks more HUNT behind the whole economy, not behind a token of its
own.

This is the core of Hunt Town's thesis: a shared economy where **the success of one
project contributes to the strength of all of them**, rather than fragmenting a community
across disconnected tokens.
