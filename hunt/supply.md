# Supply & Distribution

**A finite supply, an expanding economy.** HUNT was issued once, and no address can mint
more, so the supply story is not about emission schedules. It is about how much has been
burned, how much is locked, and how much is actually circulating.

## Fixed issuance

| | |
| --- | --- |
| **Original issuance** | 500,000,000 HUNT |
| **Inflation** | None. No address can mint, and there is no emission schedule |
| **Canonical chain** | Ethereum |

The HUNT contract has a minter role, but its only minter was removed on February 19, 2024.

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
| **Locked** | **Ethereum:** the HUNT held by the Factory NFT contract, plus the HUNT held by the Neverlose.money vault. **Base:** the live HUNT balance of the Mint Club V2 Bond contract, minus the reserve behind Mini Buildings |
| **Market circulation** | **Ethereum:** total supply minus the bridge balance, Ethereum locked HUNT, and the Ethereum dead-address balance. **Base:** the bridge balance minus Base locked HUNT and the Base dead-address balance |

**Locked** HUNT still exists, but it is committed: held by the Factory NFT contract,
time-locked in the Neverlose.money vault, or sitting in the reserves of Co-op and other
Mint Club tokens on Base. **Market circulation** is what remains: held in wallets, on
exchanges, and in liquidity pools.

Two notes on method:

- Legacy Building NFTs do not count as locked. The HUNT behind Main Buildings (held by the
  Town Hall) and behind Mini Buildings counts as circulating. On Base, the Mini Building
  reserve is read from the Mint Club V2 Bond's record for the Mini Building collection
  (1,124,100 HUNT on September 23, 2026) and subtracted from the Bond's balance.
- Market circulation is computed from these onchain reads. It is **not** an
  exchange-reported float, and it may differ from third-party circulating-supply figures.

The Neverlose.money vault is verifiable onchain:
[`0x7edBE5aF30Ba6Ba2DE9EdDc72C2f585D1B0D5775`](https://etherscan.io/token/0x9AAb071B4129B083B01cB5A0Cb513Ce7ecA26fa5?a=0x7edBE5aF30Ba6Ba2DE9EdDc72C2f585D1B0D5775).

## Why the accounting matters

The locked category is the mechanical expression of the factory's thesis: **growth tightens
supply.** Every Factory NFT minted and every token launched against a HUNT reserve moves HUNT
out of free circulation. Past burns removed HUNT permanently. None of this is a promise about
price. It is simply what the contracts do, and all of it is verifiable onchain.

The Factory NFT launch changed the accounting once. About 2.48 million HUNT behind legacy
Buildings (1,355,000 in the Town Hall and 1,124,100 in the Mini Building reserve, as of
September 23, 2026) moved from locked to circulating.

## Live figures

Supply is computed live from onchain sources rather than restated here, so this page cannot
go stale. Current burned, locked, and circulating figures are published at
**[hunt.town/factory](https://hunt.town/factory#supply)**, split by chain: the Factory NFT and the
Neverlose.money vault on Ethereum, and the Mint Club reserves on Base minus Mini Buildings.
Historic burns, the Ethereum → Base bridge balance, and dead-address balances are shown
alongside.

The reduction from 500,000,000 to today's total supply is itself documented event by event
in [Buyback & Burn](buyback-and-burn.md#the-historical-record).
