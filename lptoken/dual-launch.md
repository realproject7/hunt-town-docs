# Dual Launch

A **dual launch** creates a token and its LP vault in the same transaction, so a new market
opens with liquidity already in place and its LP side already tokenized.

## What happens at launch

1. A fixed-supply token is deployed — **1,000,000,000** tokens, minted once, with no mint,
   burn, or pause function anywhere afterwards. The creator can edit presentation metadata
   (name, image, links) and nothing else.
2. The pool is initialized: **native currency against the new token**, at a **1%** LP fee.
3. Part of the supply opens a **permanent one-sided launch position**.
4. The **LP vault** is bootstrapped over the same pool, making the LP side an lpTOKEN from
   the first block.
5. Optionally, the creator's own first buy executes atomically, with slippage and deadline
   protection and an exact refund of anything unspent.

Both the launch position and the vault sit in **one pool** — the same price, the same fee
accounting. There is no second pool to keep in sync.

## Initial shares are burned

This is the part worth being precise about. On a platform launch the bootstrap's share
recipient is a **dead address**: not merely the standard 1,000,000 dead-share floor, but
**the entire initial share supply** minted at bootstrap.

Nobody — creator, protocol, or team — holds the opening lpTOKEN supply. It cannot be
redeemed, sold, or unlocked. Every lpTOKEN share that circulates afterwards was minted by
someone depositing real assets into the vault.

## The permanent launch position

The launch position is one-sided and opened across **every price below the launch price**.
It has no withdraw function of any kind — there is no code path, privileged or otherwise,
that removes it.

Its purpose is to be **standing bid depth** underneath the market that cannot be pulled.

## The floor that grows with volume

Because the launch position permanently earns fees, and a share of those fees is routed
into vault NAV that nobody can redeem, the floor **compounds with cumulative trading volume**
rather than being fixed at the size of the initial deposit.

Roughly, per the product's own methodology:

- about **0.20%** of buy volume accrues to unredeemable NAV in the counter currency, and
- about **0.60%** of sell volume accrues in the target token.

`compound` then pairs that into bid depth that can never be withdrawn. Whatever cannot be
paired sits idle in the vault — still out of circulation, still with no claim against it.

> **This is depth, not a price guarantee.** A growing, unredeemable NAV means there is
> standing liquidity beneath the market. It does not promise any particular price, return,
> or floor level. See [Risks](risks.md).

## Curated vaults are different

A **curated LP vault** wraps a pool that already exists. It has no launchpad hook, no
one-sided launch position, no launch-fee split, and therefore **no permanent floor** — it is
purely mint, redeem, and compound over the wrapped pool. Its price range is computed
per-pool from the live supply of each leg, rather than using the launch pair's fixed range.

Curation is owner-gated: the pool must already be initialized, must be hookless, and must
meet a minimum fee tier.
