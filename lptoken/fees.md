# Fees & Economics

Every fee in lpTOKEN.fun is fixed in the contracts. There is **no performance fee and no
management fee** on the vault position — swap fees earned by the vault's own liquidity stay
with holders in full.

## The fee table

| Fee | Rate | Where it goes |
| --- | --- | --- |
| **Vault position swap fees** | the pool's LP fee | **100% to holder NAV.** No skim. |
| **Mint** (`mintPair`) | 30 bps on gross shares | Fee shares minted to the protocol treasury |
| **Redeem** | 30 bps on submitted shares | Fee shares transferred to the treasury; only the net is burned |
| **Bootstrap, ERC-20 transfers** | none | — |
| **Launch position — target leg** | the pool's LP fee | 40% creator · **60% vault NAV** |
| **Launch position — counter leg** | the pool's LP fee | 40% creator · **20% vault NAV** · 40% protocol treasury |

A minimum assessment size prevents splitting a deposit into dust to dodge the 30 bps share
fee.

## How launch fees are distributed

Fee distribution on the launch position is **permissionless** — anyone can trigger it. When
it runs:

- The **NAV legs transfer atomically** into the vault. If that transfer fails, the whole
  distribution reverts. This is what makes the backing behind lpTOKEN reliable rather than
  best-effort.
- **Creator and treasury payouts are failure-isolated retryable claims**, each with a
  bounded gas stipend, so a recipient that cannot accept a transfer can never block anyone
  else's.
- Rounding remainders carry forward between distributions, so calling it more or less often
  cannot bias the split.

The creator's claim on launch fees can be handed to another address by the current creator.
Nothing else about the position moves with it.

## What a share is worth

An lpTOKEN share is a live pro-rata claim on the vault's total assets — position principal,
accrued fees, unredeemed launch-fee NAV, and idle balances — in both currencies. See
[LP Vaults & Shares](lp-vaults.md).

## Price behaviour

Because a full-range LP position holds both sides of the pair, its value moves roughly with
the **square root** of the price ratio rather than linearly:

```
lpTOKEN value  ≈  √(P_t / P_0)      (idealized, fees excluded)
```

so an lpTOKEN share has roughly **half the price sensitivity** of holding the token
outright, plus the fee income the position earns.

> This is an idealized approximation with fees excluded, not a guaranteed volatility cap and
> not a promised return profile. Real outcomes depend on fees earned, impermanent loss, and
> how much of the pool's liquidity the vault represents. See [Risks](risks.md).

## The protocol's own backtest

The product publishes a historical model of how a vault would have behaved on a real market.
It is explicitly labelled a **historical model, not a forecast**, and its assumptions are
stated with it: a price proxy taken from an existing market's history, a hypothetical vault
sized at a fraction of pre-existing liquidity, launch fees excluded, and exactly one mint
and one redeem fee assessed.

Read it as an illustration of the mechanics, not as an expected return.
