# Supply & Distribution

**A finite supply, an expanding economy.** HUNT was issued once and has no minting function,
so the supply story is not about emission schedules. It is about how much has been burned,
how much is locked, and how much is actually circulating.

## Fixed issuance

| | |
| --- | --- |
| **Original issuance** | 500,000,000 HUNT |
| **Inflation** | None: no minting function, no emission schedule |
| **Canonical chain** | Ethereum |

Total supply is read from the canonical **Ethereum** contract. HUNT on Base is bridged and
backed 1:1: the HUNT held by the Ethereum → Base bridge stands for all of the HUNT on Base,
so Base is accounted for inside that balance rather than added on top. Counting both would
double-count the same tokens. See [Base HUNT (Bridged)](base-hunt.md).

## Three categories

Every HUNT falls into exactly one of three live categories, each measured against the
original 500,000,000 as denominator:

| Category | How it is derived |
| --- | --- |
| **Burned** | The historical reduction from the original issuance (500,000,000 minus the current Ethereum total supply), plus the live HUNT balances at the `0x…dEaD` address on Ethereum and on Base |
| **Locked** | **Ethereum:** 1,000 HUNT per Main Building, plus the HUNT held by the Neverlose.money vault. **Base:** the live HUNT balance of the Mint Club V2 Bond contract, which holds every Base HUNT reserve, including the HUNT behind Mini Buildings |
| **Market circulation** | **Ethereum:** total supply minus the bridge balance, Ethereum locked HUNT, and the Ethereum dead-address balance. **Base:** the bridge balance minus Base locked HUNT and the Base dead-address balance |

**Locked** HUNT still exists, but it is committed: held by the Town Hall contract behind Main
Buildings, time-locked in the Neverlose.money vault, or sitting in the reserves of tokens and
Mini Buildings minted through Mint Club on Base. **Market circulation** is what remains: held
in wallets, on exchanges, and in liquidity pools.

Two notes on method:

- Main Building supply mirrors the figure published at
  [hunt.town/about](https://hunt.town/about): 1,000 HUNT per Main Building. Mini Buildings are
  not counted one by one. Their HUNT is part of the Mint Club Base balance.
- Market circulation is computed from these onchain reads. It is **not** an
  exchange-reported float, and it may differ from third-party circulating-supply figures.

The Neverlose.money vault is verifiable onchain:
[`0x7edBE5aF30Ba6Ba2DE9EdDc72C2f585D1B0D5775`](https://etherscan.io/token/0x9AAb071B4129B083B01cB5A0Cb513Ce7ecA26fa5?a=0x7edBE5aF30Ba6Ba2DE9EdDc72C2f585D1B0D5775).

## Why the accounting matters

The locked and burned categories are the mechanical expression of the studio's thesis:
**growth tightens supply.** Every Building minted and every token launched against a HUNT
reserve moves HUNT out of free circulation, and every burn removes it permanently. Neither is
a promise about price. They are simply what the contracts do, and both are verifiable
onchain.

## Live figures

Supply is computed live from onchain sources rather than restated here, so this page cannot
go stale. Current burned, locked, and circulating figures are published at
**[hunt.town/hunt](https://hunt.town/hunt)**, split by chain: Main Buildings and the
Neverlose.money vault on Ethereum, the Mint Club lock-up on Base, and burns broken out into
historic burns, the bridge balance, and dead-address balances.

The reduction from 500,000,000 to today's total supply is itself documented event by event
in [Buyback & Burn](buyback-and-burn.md).
