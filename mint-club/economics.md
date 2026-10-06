# Economics

Mint Club's trading economics are built into the bonding curve. Three fees can apply: a
**creator royalty** on each mint and burn, a **protocol fee** taken out of that royalty, and
a small **creation fee** when an asset is deployed.

## Creator royalties

Creators can earn **royalties** on the trading of their asset. Each creator sets the rate
for their own asset, from 0% to 50%, and can set different rates for minting and burning.
The royalty is taken on each mint and burn, in the asset's reserve token, and accrues to the
creator, who **claims** it through the [creator tools](overview.md#creator-tools).

## Protocol fee

The protocol keeps 20% of each creator royalty. With a 0.3% royalty, the creator receives 0.24% and the protocol receives 0.06%.

Platform fees fund Mint Club's own token model: the buyback-and-burn of
[MT (Mint Token)](mint-token.md).

## Creation fee

Deploying a new token or NFT costs a nominal creation fee, set per chain (0.0007 ETH on
Base, for example).

## How fees fit the curve

The mint royalty is paid on top of the reserve deposit, and the burn royalty is taken from
the reserve paid out.
