# LP Vaults & Shares

An **LP vault** is the contract that turns a Uniswap v4 liquidity position into a
transferable ERC-20.

## One vault, one pool, one position

Each vault is pinned to **exactly one pool**. Its currency pair and fee tier are fixed at
deployment and can never be changed afterwards.

Inside that pool the vault owns **one position**, whose price range is set once when the
vault is bootstrapped and never changes.

The vault contract **is** the ERC-20 contract **and** the position owner, so an lpTOKEN
share is a direct pro-rata claim on the vault itself.

## What a share claims

A share's claim is computed live from onchain state: its pro-rata part of the position's
principal, pending position fees, pending launch-fee NAV and idle vault balances, in each of
the pair's two currencies.

## Mint

A mint deposits **both sides at the vault's current ratio** and issues shares in
proportion.

## Redeem

A redeem burns shares and pays out **in kind**: a proportional slice of the position's
liquidity plus a proportional share of idle balances, in both currencies. There is no lockup
and no admin approval; redemption is always available.

## Compound

Fees earned by the position sit as idle balances until someone pairs them back into
liquidity. Compounding does that, and it is:

- **Permissionless.** Anyone can trigger it; there is no privileged keeper.
- **Swapless.** It only pairs balances that already match; it never trades one side for the
  other, so compounding cannot move the market.

## What nobody can do

The vaults are deliberately rigid:

- **Not upgradeable.** There is no proxy and no patch path.
- **No pause, no admin withdrawal.** No privileged role can move, freeze, or seize vault
  assets.
- The factory owner can only curate **new** pools and set terms for **future** launches.
  Existing vaults and positions are untouchable.

A bug cannot be fixed in place. See [Risks](risks.md).
