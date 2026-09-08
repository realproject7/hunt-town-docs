# Supply & Distribution

**A finite supply, an expanding economy.** HUNT was issued once and has no minting
function — so the supply story is not about emission schedules, but about how much has been
burned and how much is locked inside the products the studio runs.

## Fixed issuance

| | |
| --- | --- |
| **Initial supply** | 500,000,000 HUNT |
| **Inflation** | None — no minting function, no emission schedule |
| **Canonical chain** | Ethereum |

Total supply is read from the **Ethereum** contract. Bridged HUNT on Base is a
representation of the canonical token, so it is **not** added to total supply —
double-counting it would overstate the economy. See [Base HUNT (Bridged)](base-hunt.md).

## How supply is accounted

Four figures describe the state of HUNT at any moment:

| Figure | How it is derived |
| --- | --- |
| **Burned** | Initial supply (500,000,000) − current total supply |
| **Product reserves** | HUNT held as bonding-curve reserve behind tokens launched in the ecosystem |
| **Building NFTs** | Main Buildings × 1,000 HUNT + Mini Buildings × 100 HUNT |
| **Outside reserves** | Total supply − everything locked above |

**Locked** is the sum of product reserves and Building NFTs — HUNT that exists but is held
inside the curves backing issued assets, redeemable only by burning the asset it backs.
**Outside reserves** is the remainder: HUNT held freely in wallets, on exchanges, and in
liquidity pools.

> Mini Buildings are themselves HUNT-backed assets on Base. They are counted once, in the
> Building NFTs line, and excluded from the product-reserves figure so the same HUNT is
> never counted twice.

## Why the accounting matters

The two locked categories are the mechanical expression of the studio's thesis: **growth
tightens supply.** Every project token launched and every Building minted moves HUNT out of
free circulation and into a reserve. Every buyback-and-burn removes it permanently.

Neither is a promise about price. They are simply what the contracts do, and both are
verifiable onchain.

## Live figures

Supply is computed live from onchain sources rather than restated here, so this page cannot
go stale. Current burned, locked, and outside-reserve figures are published on the studio
site at **[hunt.town/hunt](https://hunt.town/hunt)**.
