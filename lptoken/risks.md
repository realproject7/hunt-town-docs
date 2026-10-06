# Risks

Holding an lpTOKEN share is not the same as holding the token, and it is not a yield
product.

## Liquidity-provision risks

- **Impermanent loss.** When the price moves, the position ends up with more of the weaker
  asset, so it can be worth less than holding the same starting amounts of both assets
  outside the pool. Fees offset this but do not remove it.
- **Loss-versus-rebalancing (LVR).** Arbitrageurs, not the pool, capture the value of price
  moves between trades. This is a structural cost of passive liquidity provision.
- **LP competition and dilution.** Other liquidity providers, including concentrated and
  just-in-time liquidity, can take fee share away from the vault's position.
- **Routing away.** Trades can be routed to other venues or pools entirely, in which case
  the vault earns no fees from them.
- **Uniswap's protocol fee.** Uniswap governance, not lpTOKEN.fun, controls a protocol fee that
  Uniswap can deduct before LP fees. It would reduce the swap fees the vault position earns.

## Protocol risks

- **Vaults are not upgradeable.** This removes the risk of an administrator upgrading the
  vault, but **a bug cannot be fixed in place**: a flawed vault would have to be abandoned
  rather than repaired.
- **Smart-contract risk generally.** The contracts are onchain, permissionless, and final.
  Careful design reduces this risk; it does not remove it.
- **Position range limits.** A vault's price range is fixed at bootstrap. It spans every
  price a market can realistically reach, so only an extreme price would take it out of range
  and stop it earning fees.

## Token risks

- **The underlying token can go to zero.** Tokens launched on the platform are
  permissionless, user-created assets. Being launched here is not an endorsement, a vetting,
  or a guarantee of anything.
- **A floor is depth, not a price.** The permanent launch position and the NAV held by burned
  launch shares, described in [Dual Launch](dual-launch.md), create standing bid depth that cannot be
  withdrawn. They do **not** guarantee a price, a return, or that you can exit at any
  particular level.

## Nothing here is advice

The mechanics on these pages describe what the contracts do. They are not financial advice,
not an offer, and not a prediction. See [Terms](../terms.md).
