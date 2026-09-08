# LP Vaults & Shares

An **LP vault** is the contract that turns a Uniswap v4 liquidity position into a
transferable ERC-20. This page covers what a share actually claims and how minting,
redeeming, and compounding work.

## One vault, one pool, one position

Each vault is a minimal clone pinned to **exactly one pool** — its currency pair, fee tier,
tick spacing, and hook are fixed in the clone's immutable arguments at deployment and can
never be changed afterwards.

Inside that pool the vault owns **one position**, whose price range is set once when the
vault is bootstrapped and never re-derived. That matters: if the range were recomputed per
call, a later deposit could quietly move a position that holders were told was permanent.

The vault contract **is** the ERC-20 contract **and** the position owner. An lpTOKEN share
is not a wrapper or a receipt pointing somewhere else — it is a direct pro-rata claim on the
vault itself.

## What a share claims

A share's claim is computed live from onchain state, never cached:

```
claim(shares) = shares / totalSupply
              × ( position principal
                + pending position fees
                + pending launch-fee NAV
                + idle vault balances )
```

evaluated for **each** of the two currencies in the pair. So a share is backed by the
liquidity itself, plus every fee that has accrued to it and not yet been redeployed.

## Mint

`mintPair` deposits **both legs at the vault's current ratio** and issues shares in
proportion. Because a mint scales every component of the portfolio — position liquidity and
idle balances alike — by the same ratio, a depositor can never convert pre-existing idle
value at a price of their choosing.

The app also offers a single-asset convenience path that swaps into the correct ratio before
depositing, for people who hold only one side.

## Redeem

`redeem` burns shares and pays out **in kind** — a proportional slice of the position's
liquidity plus a proportional share of idle balances, in both currencies. There is no lockup
and no admin approval; redemption is always available.

## Compound

Fees earned by the position sit as idle balances until someone pairs them back into
liquidity. `compound` does that, and it is:

- **Permissionless.** Anyone can call it; there is no privileged keeper.
- **Swapless.** It only pairs balances that already match; it never trades one leg for the
  other, so compounding cannot move the market.
- **Bounded.** A single call may deploy at most half of the economically available base,
  and there is a short cooldown between calls.

Because compounding is capped and swapless, it converges over repeated calls rather than
attempting one large rebalance.

## Dead shares

At bootstrap the vault mints a fixed block of **1,000,000 dead shares** to an unrecoverable
address. This is the standard defence against the first-depositor share-price manipulation
attack: the supply can never be driven to a state where one share represents the entire
vault.

For platform launches the dead-lock goes much further — see [Dual Launch](dual-launch.md).

## What nobody can do

The vaults are deliberately rigid:

- **Not upgradeable.** There is no proxy and no patch path.
- **No pause, no admin withdrawal.** No privileged role can move, freeze, or seize vault
  assets.
- The factory owner can only curate **new** pools and set terms for **future** launches.
  Existing vaults and positions are untouchable.
- The protocol treasury address rotates only through a **two-step propose-and-accept**
  process, independent of factory ownership.

The trade-off is stated plainly on the product's own methodology page and repeated in
[Risks](risks.md): a bug cannot be fixed in place.
