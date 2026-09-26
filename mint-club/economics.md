# Economics

Mint Club's trading economics are built into the bonding curve. Three fees can apply: a
**creator royalty** on each mint and burn, a **protocol fee** taken out of that royalty, and
a small **creation fee** when an asset is deployed.

## Creator royalties

Creators can earn **royalties** on the trading of their asset. Each creator sets the rate
for their own asset, from 0% to 50%, and can set different rates for minting and burning.
The royalty is taken on each mint and burn, in the asset's reserve token, and accrues to the
creator, who **claims** it through the [creator tools](creator-tools.md). This gives
creators an ongoing, activity-based revenue stream from a healthy market in their token or
NFT, not just a one-time sale.

This royalty model is what made Mint Club attractive for consumer trading products: for
example, PumpSea used Pump.fun-style creator royalties on NFT trading (see the
[Build Log](../track-record/build-log.md)).

## Protocol fee

The protocol fee is 20% of the creator royalty. It is deducted when the creator claims. With
a 0.3% royalty, the creator receives 0.24% and the protocol receives 0.06%. If the royalty is
set to 0%, the protocol fee is 0% too.

Platform fees fund the protocol and feed back into the ecosystem, including the **MT
buyback-and-burn** program, where platform revenue is used to buy and burn
[MINT (MT)](mint-token.md), tightening its supply over time.

## Creation fee

Deploying a new token or NFT costs a nominal creation fee, set per chain (0.0007 ETH on
Base, for example). It guards against front-running on token symbols. Gas is paid
separately.

## How fees fit the curve

Because trades are against the curve rather than an order book, the royalty is applied as
part of the mint or burn transaction:

- **Mint:** the minter pays the reserve deposit plus the mint royalty.
- **Burn:** the burn royalty is taken from the reserve paid out on sale.

The split is fixed by the protocol: 80% of each royalty goes to the creator and 20% to the
protocol. The royalty rates themselves are part of each asset's configuration.
