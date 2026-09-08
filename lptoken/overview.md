# lpTOKEN.fun — Overview

**One market. Two ways to take part — the token and its liquidity.**

The token has an LP. Now the LP has a token. On lpTOKEN.fun you can trade the coin, or hold
its fee-earning liquidity as a transferable token of its own.

## The idea

In a normal AMM market there are two very different positions, and only one of them is easy
to hold. You can buy the token — simple, liquid, one balance in your wallet. Or you can
provide liquidity — which earns swap fees, but means managing an NFT position, a price
range, and a rebalancing problem.

lpTOKEN.fun makes the second position as easy to hold as the first. A **Uniswap v4
liquidity position is wrapped in an ERC-20**, so the LP side of a market becomes a token you
can mint, hold, transfer, and redeem like any other.

## What that gives you

- **Two exposures to one market.** The token tracks price. The **lpTOKEN** share tracks the
  liquidity: it holds both sides of the pair and accrues swap fees.
- **Fees stay in the vault.** Swap fees earned by the position are not skimmed — they remain
  in the vault and back every share. Anyone can permissionlessly compound idle balances
  into more liquidity.
- **A market from day one.** Builders can launch a token and its LP together, with the
  initial liquidity permanently locked, instead of bootstrapping a pool afterwards.

## Two ways a market gets here

| Path | What it is |
| --- | --- |
| **Dual launch** | Launch a new token and its LP vault together on the platform. Initial shares are permanently burned, and a one-sided launch position creates a floor that grows with volume. See [Dual Launch](dual-launch.md). |
| **Curated LP vault** | Wrap an existing Uniswap v4 pool in a vault so its liquidity becomes an lpTOKEN. No launch position, no floor — pure mint / redeem / compound. |

## Where it runs

lpTOKEN.fun is **live** on **Base** and **Robinhood Chain**. Contract addresses are listed
in [Contracts & Addresses](../reference/contracts.md).

## Why the studio built it

A token economy needs more than a price chart. Giving a market a liquidity token means the
depth behind it is something anyone can hold, price, and use — and it gives builders a real
market on day one rather than a launch followed by a liquidity problem.

Read on: [LP Vaults & Shares](lp-vaults.md) · [Dual Launch](dual-launch.md) ·
[Fees & Economics](fees.md) · [Risks](risks.md).
