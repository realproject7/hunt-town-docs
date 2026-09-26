# Factory NFT: Overview

**The Factory NFT is the one asset that Hunt Town's products back.** You lock HUNT to mint
one. Product revenue, marketplace royalties and burn fees add more HUNT to the vault, which
raises the NAV of every NFT at once. Burn any time to take 95% of your NFT's NAV back in
HUNT.

Hunt Town runs many products. The Factory NFT ties them to one asset, counted in HUNT.

## At a glance

| | |
| --- | --- |
| **Network** | Ethereum mainnet |
| **Standard** | ERC-1155, token id `0` |
| **Supply** | Unlimited. Minted at NAV, burned for 95% of NAV |
| **Lock-up per NFT** | 1,000 HUNT × the multiplier (1,000 HUNT at launch) |
| **Pay with** | HUNT, or ETH, USDC or USDT swapped to HUNT in the same transaction |
| **Backed by** | HUNT, held by the Factory NFT contract itself |
| **At launch** | One seed NFT backed by 1,000 HUNT (×1.0000) |
| **Minimum supply** | One. The last NFT cannot be burned |
| **Burn fee** | 5%, stays in the vault |
| **Marketplace royalty** | 3% |
| **Upgradeable** | No |

## How it works

1. **Mint at NAV.** Anyone can mint by locking the current NAV per NFT in HUNT. At launch
   that is 1,000 HUNT. You can also pay with ETH, USDC or USDT, which is swapped to HUNT in
   the same transaction.
2. **The vault grows.** Any HUNT added to the contract outside a mint raises the NAV per NFT
   for every holder at once. There is nothing to claim and no holding period.
3. **Burn for HUNT.** Burning an NFT redeems 95% of its NAV in HUNT. The other 5% stays in
   the vault, which raises the NAV for everyone still holding.

Details: [Mint & Burn](mint-and-burn.md) · [The NAV Vault](nav-vault.md).

## NAV and the multiplier

**NAV per NFT** is the HUNT in the vault divided by the number of NFTs, rounded down.

The **multiplier** shows how far the NAV per NFT has moved from its starting point:

```
multiplier = NAV per NFT ÷ 1,000 HUNT
```

At launch the multiplier is ×1.0000. A NAV per NFT of 1,050 HUNT reads as ×1.0500, and
minting one NFT then locks 1,050 HUNT.

## Where the HUNT comes from

- Revenue from Hunt Town's products
- Royalties from NFT marketplace sales (3%)
- The burn fee (5%)
- Other income

There is no deposit schedule and no set amount. See [The NAV Vault](nav-vault.md).

## What the owner can and cannot do

The contract owner can change three things:

- the metadata,
- the royalty operator, which receives the 3% royalty, and
- the transfer validator, which sets the rules for transfers between wallets, including
  trades on NFT marketplaces.

The owner can also hand ownership to another address, in two steps, or give it up. The
owner cannot withdraw the HUNT in the vault, mint NFTs that are not backed by HUNT, or
upgrade the contract. The 3% royalty and the 5% burn fee are fixed in the contract. The
transfer validator never applies to minting or burning.

## Counted in HUNT

The lock-up, the NAV and what a burn gives back are all counted in HUNT. The dollar value
follows the HUNT price, and it can fall. If the multiplier has not risen enough since you
minted, a burn gives back less HUNT than you locked, because of the 5% fee. No return is
promised. See [What you get back in HUNT](mint-and-burn.md#what-you-get-back-in-hunt) and
[Terms](../terms.md).

## Building NFTs

Main and Mini Building NFTs are legacy assets. Holders can turn them into Factory NFTs, one
way. See [Migrating Buildings](migrating-buildings.md).

## Where to use it

Mint and burn at [hunt.town/factory](https://hunt.town/factory). The page also shows the
live NAV per NFT, multiplier, supply and vault HUNT, and an example of how vault growth
changes what a burn gives back.
