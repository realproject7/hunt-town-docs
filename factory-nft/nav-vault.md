# The NAV Vault

The vault is not a separate contract. The Factory NFT contract holds the HUNT itself, and
its HUNT balance is the vault. Anyone can read it onchain at any time.

## NAV per NFT

```
NAV per NFT = HUNT in the vault ÷ NFTs in supply, rounded down
multiplier  = NAV per NFT ÷ 1,000 HUNT
```

The Factory NFT launched with one seed NFT backed by 1,000 HUNT: a NAV per NFT of 1,000
HUNT and a multiplier of ×1.0000. The team holds the seed. It is an ordinary Factory NFT
with no special rights.

## What raises the NAV

Any HUNT added to the Factory NFT contract outside a mint raises the NAV per NFT for every
holder at the same moment. (A mint brings in its own share, so the NAV stays the same.)
There is nothing to claim, no checkpoint, and no holding period. An NFT minted today carries
the same share as one minted at launch.

HUNT comes in from four sources:

- **Revenue from Hunt Town's products.** Product revenue is used to buy HUNT, and that HUNT
  is sent to the vault.
- **Royalties from NFT marketplace sales (3%).** The contract sets a 3% royalty (ERC-2981),
  paid to a royalty operator by the marketplaces that honor it. The operator buys HUNT with
  it and deposits that HUNT into the vault.
- **The burn fee (5%).** When an NFT is burned, 5% of its NAV stays in the vault.
- **Other income.**

There is no deposit schedule, and the amounts are not fixed. No inflow is promised.

## What each action does

| Action | HUNT in the vault | NFTs in supply | NAV per NFT |
| --- | --- | --- | --- |
| HUNT arrives | Rises | No change | Rises |
| Someone mints | Rises by the HUNT they lock | Rises | No change |
| Someone burns | Falls by 95% of the burned NFTs' NAV | Falls | Rises |

Rounding on mints and burns leaves small remainders in the vault.

## Safeguards

- The contract cannot be upgraded.
- The owner cannot withdraw HUNT from the vault or mint NFTs without HUNT behind them.
- The owner can change only the metadata, the royalty operator, and the transfer validator,
  and can hand ownership over or give it up. The transfer validator never applies to minting
  or burning.
- The 3% royalty and the 5% burn fee are fixed in the contract.
- Supply can never drop below one NFT, so there is always an NFT for the vault's HUNT to
  back.

## Counted in HUNT

The NAV is counted in HUNT. Its dollar value follows the HUNT price and moves with it, in
either direction. See [Terms](../terms.md).

## Live numbers

The live NAV per NFT, multiplier, supply, and vault HUNT are shown at
[hunt.town/factory](https://hunt.town/factory#vault). The vault's HUNT also counts as locked in
[Supply & Distribution](../hunt/supply.md).
