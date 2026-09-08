# Risks

Holding an lpTOKEN share is not the same as holding the token, and it is not a yield
product. These are the risks the protocol names for itself.

## Liquidity-provision risks

- **Impermanent loss.** A liquidity position holds both sides of a pair. When the price
  moves, the position ends up with more of the weaker asset and less of the stronger one, so
  it can be worth less than simply having held either asset. Fee income offsets this; it
  does not eliminate it.
- **Loss-versus-rebalancing (LVR).** Arbitrageurs, not the pool, capture the value of price
  moves between trades. This is a structural cost of passive liquidity provision.
- **LP competition and dilution.** Other liquidity providers — including concentrated and
  just-in-time liquidity — can take fee share away from the vault's position.
- **Routing away.** Trades can be routed to other venues or pools entirely, in which case
  the vault earns no fees from them.

## Protocol risks

- **Vaults are not upgradeable.** There is no proxy and no admin patch path. This removes
  admin risk, but it also means **a bug cannot be fixed in place**. A flawed vault would
  have to be abandoned rather than repaired.
- **Smart-contract risk generally.** The contracts are onchain, permissionless, and final.
  Audits and careful design reduce this risk; they do not remove it.
- **Position range limits.** A vault's price range is pinned at bootstrap. Prices can move
  outside the range, in which case the position stops earning fees until price returns.

## Token risks

- **The underlying token can go to zero.** Tokens launched on the platform are
  permissionless, user-created assets. Being launched here is not an endorsement, a vetting,
  or a guarantee of anything.
- **A floor is depth, not a price.** The permanent launch position and unredeemable NAV
  described in [Dual Launch](dual-launch.md) create standing bid depth that cannot be
  withdrawn. They do **not** guarantee a price, a return, or that you can exit at any
  particular level.

## Nothing here is advice

The mechanics on these pages describe what the contracts do. They are not financial advice,
not an offer, and not a prediction. See [Terms](../terms.md).
