# Fees & Economics

Every fee in lpTOKEN.fun is fixed in the contracts. There is **no performance fee and no
management fee** on the vault position. Swap fees earned by the vault's own liquidity stay
with holders in full.

## The fee table

| Fee | Rate | Where it goes |
| --- | --- | --- |
| **Vault position swap fees** | the pool's LP fee | **100% to holder NAV.** No skim. |
| **Mint** | 0.3% | Protocol treasury |
| **Redeem** | 0.3% | Protocol treasury |
| **Bootstrap, ERC-20 transfers** | none | n/a |
| **Launch position, target leg** | the pool's LP fee | 40% creator · **60% vault NAV** |
| **Launch position, counter leg** | the pool's LP fee | 40% creator · **20% vault NAV** · 40% protocol treasury |

## How launch fees are distributed

Fee distribution on the launch position is **permissionless**: anyone can trigger it. When
it runs:

- The **NAV part of the fees goes straight into the vault**.
- **Creator and treasury payouts are separate claims** that can be retried, so a recipient
  that cannot accept a transfer never blocks anyone else's.

The creator's claim on launch fees can be handed to another address by the current creator.
Nothing else about the position moves with it.

## Price behaviour

Because a full-range LP position holds both sides of the pair, its value moves roughly with
the **square root** of the price ratio rather than linearly:

```
V_t / V_0  ≈  √(P_t / P_0)      (idealized, fees excluded)
```

Here P is the token's price in the pair's other asset, such as ETH or USDC, and V is the
value of an lpTOKEN share measured in that same asset. Measured that way, an lpTOKEN share
has roughly **half the price sensitivity** of holding the token outright, plus the swap fees
the position earns. In a pair against ETH, the dollar value also moves with ETH, so this
does not mean half the volatility in dollars.

> An idealized approximation, not a promised volatility cap or return. Real outcomes depend
> on fees earned, impermanent loss, and how much of the pool's liquidity the vault
> represents. See [Risks](risks.md).

## How it works

The product explains its full model at
[lptoken.fun/methodology](https://lptoken.fun/methodology).
