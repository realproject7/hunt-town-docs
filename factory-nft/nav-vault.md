# The NAV Vault

The vault is not a separate contract. The Factory NFT contract holds the HUNT itself, and
its HUNT balance is the vault.

## NAV per NFT

```
NAV per NFT = HUNT in the vault ÷ NFTs in supply
multiplier  = NAV per NFT ÷ 1,000 HUNT
```

The Factory NFT launched with one seed NFT backed by 1,000 HUNT: a NAV per NFT of 1,000
HUNT and a multiplier of ×1.0000. The team holds the seed. It is an ordinary Factory NFT
with no special rights.

## What raises the NAV

Any HUNT added to the Factory NFT contract outside a mint raises the NAV per NFT for every
holder at the same moment. There is nothing to claim and no holding period. An NFT minted
today carries the same share as one minted at launch.

HUNT comes in from product revenue, marketplace royalties, the burn fee and other income:

- **Product revenue.** It is used to buy HUNT, and that HUNT is deposited into the vault.
- **Royalties from NFT marketplace sales (3%).** The contract sets a 3% royalty (ERC-2981),
  paid to a royalty operator by the marketplaces that honor it. The operator buys HUNT with
  it and deposits that HUNT into the vault.
- **The burn fee (5%).** When an NFT is burned, 5% of its NAV stays in the vault.

There is no deposit schedule, and the amounts are not fixed. No inflow is promised. The NAV
is counted in HUNT, so its dollar value moves with the HUNT price, in either direction. See
[Terms](../terms.md).

<figure><img src="../.gitbook/assets/site/site-factory-vault.jpg" alt="How HUNT reaches the vault"><figcaption><p>How HUNT reaches the vault, on hunt.town/factory. The numbers are an example, not a forecast.</p></figcaption></figure>

## What each action does

| Action | HUNT in the vault | NFTs in supply | NAV per NFT |
| --- | --- | --- | --- |
| HUNT arrives | Rises | No change | Rises |
| Someone mints | Rises by the HUNT they lock | Rises | No change |
| Someone burns | Falls by 95% of the burned NFTs' NAV | Falls | Rises |

## Safeguards

- The contract cannot be upgraded.
- The owner cannot withdraw HUNT from the vault or mint NFTs without HUNT behind them.
- The owner can change only the metadata and the royalty operator, and can hand ownership
  over or give it up.
- The 3% royalty and the 5% burn fee are fixed in the contract.
- Supply can never drop below one NFT, so there is always an NFT for the vault's HUNT to
  back.

## Live numbers

The live NAV per NFT, multiplier, supply, and vault HUNT are shown at
[hunt.town/factory](https://hunt.town/factory#vault). The vault's HUNT also counts as locked in
[Supply & Distribution](../hunt/supply.md).
