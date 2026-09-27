# Mint Club: Overview

**Mint Club is a no-code bonding-curve protocol** for creating and trading tokens and NFTs.
Anyone can deploy a token (ERC-20) or an NFT collection (ERC-1155) on a customizable bonding
curve, with no smart-contract code and no seeded liquidity pool, and the asset is instantly
mintable and burnable against its reserve.

For Hunt Town, Mint Club is both an **active product** and the **protocol primitive** that
much of the ecosystem is built on: Co-op project tokens, legacy Mini Buildings, and many of the
products in the [Build Log](../track-record/build-log.md) (1s.market, Memberify, Farcards,
MCDegen, Hamcaster, PumpSea, Hyped.club, MintDrop) were issued on Mint Club's curves.

## What you can do

- **Create** an ERC-20 token or ERC-1155 NFT on a bonding curve, choosing the curve shape
  and the reserve token that backs it. See [Create Assets](create.md).
- **Mint and burn** against the curve: buying mints new supply and pushes price up along the
  curve; selling burns supply and returns reserve. See [Mint & Burn](mint-burn.md).
- **Use creator tools:** airdrops, lock-ups, free minting, ownership transfer, royalty
  claims. See [Creator Tools](creator-tools.md).

## Why bonding curves

A bonding curve replaces the usual "launch a token, then go find liquidity" problem: the
curve itself is the market, with a price to mint or burn at from the start and a reserve held
behind the supply. Creators choose a curve and a reserve and deploy, with no code. See
[Bonding Curves](bonding-curves.md).

## How it relates to HUNT

Mint Club supports many reserve tokens, but it is tightly woven into the Hunt Town economy:
**HUNT-backed** tokens use HUNT as their reserve (the basis of the
[Co-op](../co-op/overview.md)), and Mint Club's own platform token, **MINT (MT)**, is itself
a HUNT-backed child token. See [MINT Token](mint-token.md).

> Full Mint Club product documentation, including event and campaign material not relevant to
> this whitepaper, lives at **docs.mint.club**. This section covers the core protocol.
