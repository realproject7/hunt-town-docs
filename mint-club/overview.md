# Mint Club — Overview

**Mint Club is a no-code bonding-curve protocol** for creating and trading tokens and NFTs.
Anyone can deploy a token (ERC-20) or an NFT collection (ERC-1155) on a customizable bonding
curve — no smart-contract code, no seeded liquidity pool — and the asset is instantly
mintable and burnable against its reserve.

For Hunt Town, Mint Club is both an **active product** and the **protocol primitive** that
much of the ecosystem is built on: Co-op project tokens, Building NFTs, and many of the
products in the [Build Log](../track-record/build-log.md) (1s.market, Memberify, Farcards,
MCDegen, Hamcaster, PumpSea, Hyped.club, MintDrop) were issued on Mint Club's curves.

## What you can do

- **Create** an ERC-20 token or ERC-1155 NFT on a bonding curve, choosing the curve shape
  and the reserve token that backs it — see [Create Assets](create.md).
- **Mint and burn** against the curve: buying mints new supply and pushes price up along the
  curve; selling burns supply and returns reserve — see [Mint & Burn](mint-burn.md).
- **Use creator tools** — airdrops, lock-ups, free minting, ownership transfer, royalty
  claims — see [Creator Tools](creator-tools.md).

## Why bonding curves

A bonding curve replaces the usual "launch a token, then go find liquidity" problem with a
deterministic, reserve-backed market:

- **Instant liquidity.** The curve itself is the market; there is always a price to mint or
  burn at, with no DEX pool to seed.
- **Reserve-backed.** Every token/NFT is backed by a reserve asset held in the curve, so
  there is real value behind the supply.
- **No-code.** Creators choose a curve and a reserve and deploy — the protocol handles the
  rest.

## How it relates to HUNT

Mint Club supports many reserve tokens, but it is tightly woven into the Hunt Town economy:
**HUNT-backed** tokens use HUNT as their reserve (the basis of the
[Co-op](../co-op/overview.md) and [Building NFTs](../hunt/building-nfts.md)), and Mint Club's
own platform token, **MINT (MT)**, is itself a HUNT-backed child token — see
[MINT Token](mint-token.md).

> Full Mint Club product documentation, including event and campaign material not relevant to
> this whitepaper, lives at **docs.mint.club**. This section covers the core protocol.
