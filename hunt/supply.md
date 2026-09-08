# Supply & Distribution

**A finite supply, an expanding economy.** HUNT was issued once and has no minting function,
so the supply story is not about emission schedules. It is about how much has been burned,
how much is locked, and how much is actually circulating.

## Fixed issuance

| | |
| --- | --- |
| **Original issuance** | 500,000,000 HUNT |
| **Inflation** | None — no minting function, no emission schedule |
| **Canonical chain** | Ethereum |

Total supply is read from the **Ethereum** contract. Bridged HUNT on Base is **not** added,
because it is backed 1:1 by canonical Ethereum HUNT — counting both would double-count the
same tokens. See [Base HUNT (Bridged)](base-hunt.md).

## Three categories

Every HUNT falls into exactly one of three live categories, each measured against the
original 500,000,000 as denominator:

| Category | How it is derived |
| --- | --- |
| **Burned** | Original issuance − the canonical Ethereum token's current total supply |
| **Locked in Building NFTs & Neverlose.money** | Main Buildings × 1,000 HUNT + Mini Buildings × 100 HUNT + the HUNT balance held by the Neverlose.money vault on Ethereum |
| **Market circulation** | Current Ethereum supply − the locked categories above |

**Locked** HUNT still exists, but it is committed: held inside the curves backing Building
NFTs, or time-locked in the Neverlose.money vault. **Market circulation** is what remains —
held in wallets, on exchanges, and in liquidity pools.

Two notes on method:

- Building NFT reads mirror the calculation published at
  [hunt.town/about](https://hunt.town/about).
- Market circulation follows the token-supply workbook's own methodology. It is **not** an
  exchange-reported float, and it may differ from third-party circulating-supply figures.

The Neverlose.money vault is verifiable onchain:
[`0x7edBE5aF30Ba6Ba2DE9EdDc72C2f585D1B0D5775`](https://etherscan.io/token/0x9AAb071B4129B083B01cB5A0Cb513Ce7ecA26fa5?a=0x7edBE5aF30Ba6Ba2DE9EdDc72C2f585D1B0D5775).

## Why the accounting matters

The locked and burned categories are the mechanical expression of the studio's thesis:
**growth tightens supply.** Every Building minted moves HUNT out of free circulation and
into a reserve; every burn removes it permanently. Neither is a promise about price — they
are simply what the contracts do, and both are verifiable onchain.

## Live figures

Supply is computed live from onchain sources rather than restated here, so this page cannot
go stale. Current burned, locked, and circulating figures — with the split across Main
Buildings, Mini Buildings, and Neverlose.money — are published at
**[hunt.town/hunt](https://hunt.town/hunt)**.

The reduction from 500,000,000 to today's total supply is itself documented event by event
in [Buyback & Burn](buyback-and-burn.md).
