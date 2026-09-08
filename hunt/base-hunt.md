# Base HUNT (Bridged)

HUNT is native to **Ethereum mainnet** and bridged to **Base**, so the same asset backs
activity on both networks. This matters because the studio's most active surfaces — Mini
Buildings, Co-op backing, Mint Club, lpTOKEN.fun, and h402 payments — live on Base, where
fees are low enough for the daily, high-frequency interactions these products depend on.

## Why two networks

- **Ethereum mainnet** holds the canonical HUNT token and the Main Building NFT — the
  high-value, long-term anchor of the economy.
- **Base** carries the day-to-day activity: Mini Buildings, project-token minting, liquidity
  markets, and agent payments, where transactions need to be cheap and fast.

## Backed 1:1

Bridged HUNT on Base is a representation of the canonical Ethereum token, **backed 1:1**.
It is the same asset, usable in reserves and payments on Base without round-tripping to
mainnet for every interaction.

Because of that 1:1 backing, Base HUNT is **not added to total supply** — counting it
alongside the Ethereum token would double-count the same tokens. All supply figures are read
from the canonical Ethereum contract. See [Supply & Distribution](supply.md).

## Bridging

HUNT moves between Ethereum and Base through Base's canonical **`L2StandardBridge`**, which
supports two-way transfers using standard Layer 2 bridging.

The supported route is **[Superbridge](https://superbridge.app/?fromChainKey=eth&fromTokenAddress=0x9AAb071B4129B083B01cB5A0Cb513Ce7ecA26fa5&toChainKey=base&toTokenAddress=0x37f0c2915CeCC7e977183B8543Fc0864d03E064C)**,
an interface to that canonical bridge — the link above is pre-filled for HUNT in the
Ethereum → Base direction. Background on the expansion to Base is in the
[announcement](https://news.hunt.town/p/expand-hunt-to-base-chain-bridge).

> **Third-party infrastructure.** The bridge contracts and their interfaces are operated by
> third parties, not by the Hunt Town Core Team. The team does not operate, control, or
> maintain them and is not responsible for vulnerabilities, failures, or interface errors
> arising from the bridging process. Users are responsible for using the bridge correctly.
> See [Terms](../terms.md).

## Contracts

| Network | Token | Address |
| --- | --- | --- |
| Ethereum | HUNT (canonical ERC-20) | `0x9AAb071B4129B083B01cB5A0Cb513Ce7ecA26fa5` |
| Base | HUNT (bridged) | `0x37f0c2915CeCC7e977183B8543Fc0864d03E064C` |
