# Fees & Risks

## Fees

| Fee | Amount |
| --- | --- |
| **Aeromax.fun fee** | 0.015% of the principal that enters or leaves through Aeromax.fun |
| **Performance fee** | None. AERO rewards and LP fees are not charged |
| **Swaps** | When a deposit or exit swaps tokens, the pool's swap fee and price impact apply. The app shows the price impact and uses 0.50% slippage |
| **Gas** | Paid in ETH on Base, separately |

The New range card states the fee before you deposit ("Entry fee included").

## Custody

- **Staked positions sit in Aerodrome's gauge.** A new range is an Aerodrome position NFT,
  staked in the pool's gauge with your wallet recorded as its owner. Aeromax.fun does not
  hold it.
- **You can always leave through Aerodrome.** Because the position and its withdrawal right
  are yours, you can also exit through Aerodrome directly, without Aeromax.fun or its fee.
- **Staking changes what you earn.** A staked position earns AERO emissions instead of the
  pool's swap fees.

## Risks

- **Out of range, no rewards.** A range earns only while the price is inside it. Outside it,
  the position holds one token and earns nothing until the price comes back.
- **Price moves change your assets.** As the price crosses your range, the position's mix of
  the two tokens changes, and its value can end up lower than simply holding them.
- **AERO is a token too.** Rewards are paid in AERO, so their dollar value follows the AERO
  price.
- **Lock-up on rewards.** AERO cannot be collected until the gauge's unlock period ends, and
  an early exit forfeits part of the accrued AERO.
- **The APR is an estimate.** It uses current emissions and staked liquidity, and it changes
  as both change. No return is promised.
- **USD values are indicative.** They come from pool prices with USDC counted at $1, not from
  an oracle. Unknown prices show a dash.
- **Public data can lag.** The chart and positions read public Base endpoints, which can
  throttle or fall behind. The app shows when a refresh fails.
- **No independent audit.** Aeromax.fun's contracts have not had an independent security
  audit.
