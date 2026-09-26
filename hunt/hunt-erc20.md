# HUNT (ERC20)

**HUNT is the token that connects Hunt Town's product economy.** It backs the
[Factory NFT](../factory-nft/overview.md), and it is the reserve asset underneath the token
economies the factory launches.

Many products. One HUNT.

| | |
| --- | --- |
| **Launched** | 2018 (the ERC-20 contract dates from February 2019) |
| **Networks** | Ethereum (canonical) · Base (bridged) |
| **Issuance** | Fixed: 500,000,000 HUNT, no inflation |
| **Standard** | ERC-20 |

## The core asset: the Factory NFT

Every Factory NFT holds an equal share of the HUNT in the Factory NFT contract on
Ethereum. Minting locks HUNT at the current NAV, and burning takes 95% of the NAV back, all
counted in HUNT. Revenue from Hunt Town's products buys more HUNT for the vault, and
marketplace royalties and burn fees add to it.

There is no fixed schedule for these purchases, and no amount is promised. See
[Factory NFT](../factory-nft/overview.md) and [The NAV Vault](../factory-nft/nav-vault.md).

## The reserve for the tokens we launch

HUNT is also the reserve asset underneath the token economies the factory ships. That gives
individual product economies a common foundation instead of a fresh, disconnected token each
time.

In the [Co-op](../co-op/overview.md), HUNT **backs project tokens** in bonding-curve
reserves. See [HUNT as the Reserve Token](reserve-token.md).

Because HUNT has no emission schedule, the only way project tokens and Factory NFTs come
into existence is by **locking existing HUNT**. Ecosystem activity tightens supply rather
than diluting it.

## Supply

HUNT was issued once, with a fixed initial supply of **500,000,000**. The HUNT contract has
a minter role, but its only minter was removed on February 19, 2024. No address can mint
HUNT, so the total supply cannot grow. Past burns reduced it, and each one is recorded in
[Buyback & Burn](buyback-and-burn.md).

The Ethereum token is canonical. Bridged HUNT on Base is a representation of it and is
**not** added to total supply. For how supply is measured and what "locked" means, see
[Supply & Distribution](supply.md).

## Contracts

| Network | Address |
| --- | --- |
| Ethereum (HUNT) | `0x9AAb071B4129B083B01cB5A0Cb513Ce7ecA26fa5` |
| Base (HUNT, bridged) | `0x37f0c2915CeCC7e977183B8543Fc0864d03E064C` |

See [Base HUNT (Bridged)](base-hunt.md) for bridge details,
[Contracts & Addresses](../reference/contracts.md) for the full list, and
[Links & Resources](../reference/links.md) for where HUNT trades.
