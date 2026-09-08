# Economics

Mint Club's trading economics are built into the bonding curve. Every mint and burn can carry
two kinds of fee: **creator royalties**, which go to the asset's creator, and **platform
fees**, which go to the protocol.

## Creator royalties

Creators can earn **royalties** on the trading of their asset. A configured royalty is taken
on mint/burn activity and accrues to the creator, who **claims** it through the
[creator tools](creator-tools.md). This gives creators an ongoing, activity-based revenue
stream from a healthy market in their token or NFT — not just a one-time sale.

This royalty model is what made Mint Club attractive for consumer trading products: for
example, PumpSea used Pump.fun-style creator royalties on NFT trading (see the
[Build Log](../track-record/build-log.md)).

## Platform fees

Mint Club takes a **platform fee** on trading activity. Platform fees fund the protocol and
feed back into the ecosystem — including the **MT buyback-and-burn** program, where platform
revenue is used to buy and burn [MINT (MT)](mint-token.md), tightening its supply over time.

## How fees fit the curve

Because trades are against the curve rather than an order book, fees are applied as part of
the mint/burn transaction:

- **Mint** — the minter pays the reserve deposit plus applicable fees.
- **Burn** — fees are applied to the reserve returned on sale.

The exact split between creator royalty and platform fee is part of the asset's
configuration and the protocol's parameters.
