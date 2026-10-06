# Base HUNT (Bridged)

HUNT is native to **Ethereum mainnet** and bridged to **Base**, so the same asset backs
activity on both networks. Ethereum holds the canonical HUNT token and the
[Factory NFT](../factory-nft/overview.md). Base carries the day-to-day HUNT activity: minting
and trading the HUNT-backed tokens of the Co-op and Mint Club.

## Backed 1:1

Bridged HUNT on Base is a representation of the canonical Ethereum token, **backed 1:1**.
It is the same asset, usable in reserves and payments on Base. It is not counted twice in
total supply. See [Supply & Distribution](supply.md).

## Bridging

HUNT moves between Ethereum and Base through Base's canonical Standard Bridge. The supported
route is
**[Superbridge](https://superbridge.app/?fromChainKey=eth&fromTokenAddress=0x9AAb071B4129B083B01cB5A0Cb513Ce7ecA26fa5&toChainKey=base&toTokenAddress=0x37f0c2915CeCC7e977183B8543Fc0864d03E064C)**,
an interface to that bridge. Background:
[announcement](https://news.hunt.town/p/expand-hunt-to-base-chain-bridge).

> The bridge and its interfaces are run by third parties, not by Hunt Town. See
> [Terms](../terms.md).

Addresses: [Contracts & Addresses](../reference/contracts.md).
