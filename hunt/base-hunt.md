# Base HUNT (Bridged)

HUNT is native to **Ethereum mainnet** and bridged to **Base**, so the same reserve asset
backs activity on both networks. This matters because the studio's most active surfaces —
Mini Buildings, Co-op backing, Mint Club, and h402 payments — live on Base, where fees are
low enough for the daily, high-frequency interactions these products depend on.

## Why two networks

- **Ethereum mainnet** holds the canonical HUNT token and the Main Building NFT — the
  high-value, long-term anchor of the economy.
- **Base** carries the day-to-day activity: Mini Buildings, project-token minting, and
  agent payments, where transactions need to be cheap and fast.

Bridged HUNT on Base is the same asset, represented on Base so it can be used in reserves
and payments there without round-tripping to mainnet for every interaction.

## Contracts

| Network | Token | Address |
| --- | --- | --- |
| Ethereum | HUNT | `0x9AAb071B4129B083B01cB5A0Cb513Ce7ecA26fa5` |
| Base | HUNT (bridged) | `0x37f0c2915CeCC7e977183B8543Fc0864d03E064C` |

> **TODO (operator):** state which canonical bridge is used for HUNT between Ethereum and
> Base, and link the bridge UI, so holders have a single supported path documented here.
