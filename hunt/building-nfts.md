# Building NFTs

**Building NFTs** are Hunt Town's membership and backing-power asset. Each one is backed
by HUNT through its own bonding-curve pool, so minting a Building both grants the holder
standing in the ecosystem and locks more HUNT out of circulation.

There are two tiers:

| Tier | Network | Standard | HUNT backing |
| --- | --- | --- | --- |
| **Main Building** | Ethereum mainnet | ERC-721 | 1,000 HUNT |
| **Mini Building** | Base | ERC-1155 (token id `0`) | 100 HUNT |

A Main Building is worth **10 Mini Buildings** in backing terms (1,000 ÷ 100), a ratio
that recurs anywhere Buildings are counted.

## What Buildings do

- **Backing power** — Buildings determine how much support a backer can give builders.
  In the [Co-op](../co-op/overview.md), holders receive **Daily Backing Points (BP)**
  based on the Mini Buildings they hold, which they spend to mint the project tokens they
  want to support.
- **HUNT locking** — each Building is backed by HUNT in a bonding-curve pool. As more
  Buildings are minted, more HUNT is locked, tightening supply and deepening the
  ecosystem's total value locked.
- **Recurring allowances** — historically, Buildings have powered recurring daily
  allowances (e.g. Hunt Tip's tipping allowance: Main = 1,000 / Mini = 100 per day), a
  pattern the studio reuses across products.

## Contracts

| Building | Network | Address |
| --- | --- | --- |
| Main Building NFT | Ethereum mainnet | `0x0c9Bb1ffF512a5B4F01aCA6ad964Ec6D7fC60c96` |
| Mini Building NFT | Base | `0x475f8E3eE5457f7B4AAca7E989D35418657AdF2a` |

The Town Hall and Building contracts were audited by BEOSIN (completed December 6, 2022) —
[announcement](https://news.hunt.town/p/hunt-town-security-audit-is-completed) ·
[report (PDF)](https://beosin.com/audits/Hunt-Town_202212051700.pdf). See
[Links & Resources → Security & Audits](../reference/links.md) for the full audit list.

> **TODO (operator):** add total issued counts for Main and Mini Buildings (and any cap),
> plus the cumulative HUNT locked in Building pools.

---

## Under consideration: Building NFT credits for h402

> **Status: proposed.** The mechanic below was implemented and tested in the h402 codebase,
> then pulled from the launch MVP. It is documented here as a **future addition under
> review**, not a live feature.

A natural way to connect Building NFTs to the studio's newest product is to let Buildings
**fund agent payments on [h402](../h402/overview.md)**. The idea: Building holders receive
a **recurring h402 credit** — a stablecoin-denominated allowance, usable to pay for h402
route calls — simply for holding Buildings. It turns a membership asset into ongoing,
real utility on the agent-payments network.

The prototype worked as follows.

### Credit amounts

Credits are denominated in micro-USD and scale with Building holdings:

| Holding | Backing units | Weekly credit |
| --- | --- | --- |
| 1 Mini Building | 1 unit | **$0.50 / week** |
| 1 Main Building | 10 units | **$5.00 / week** |

A wallet's weekly credit is:

```
units        = (main_buildings × 10) + mini_buildings
weekly_credit = units × $0.50
```

— the same 10:1 Main-to-Mini ratio used everywhere else.

### Weekly snapshot

Credits are granted on a **weekly cycle** anchored to the start of the UTC week
(Monday 00:00 UTC):

- At the snapshot, the holder's Building balances are read **on-chain** (`balanceOf` on
  the Main Building contract on Ethereum and the Mini Building contract on Base) at the
  block corresponding to the week start.
- The week's credit is granted from that balance and **resets each week** — unused credit
  does not roll over indefinitely; a fresh allowance is issued each cycle.
- If a holder acquires more Buildings mid-week, the additional credit can be topped up for
  the current week rather than waiting for the next snapshot.

### Delegation

Holders can **delegate** their Building-derived credit to other wallets, in **Mini
Building units**. This lets, for example, a holder fund an agent's wallet or a teammate's
wallet directly:

- Delegation is expressed in Mini Building units and capped at the holder's actual
  balance — you cannot delegate more units than you hold.
- Undelegated units stay with the owner; delegated units are granted to the delegate at
  the weekly snapshot.
- Delegations are managed by the holder (create / update / remove) and take effect from
  the next snapshot.

### How credits are spent

Credits integrate with h402's payment flow through the **`h402-credit` x402 extension**:
a route's payment metadata advertises that credit can be applied, and when a holder (or a
delegate) calls a paid route, available credit is **drawn down before any USDC is
charged**. Only the remainder, if any, settles as a normal Base USDC payment. See
[How Paying Works](../h402/how-paying-works.md) for the underlying x402 flow.

> **Why it's under review:** the program was removed from the h402 launch MVP (replaced by
> a simpler bonus-credit mechanism) to keep the initial release lean. The mechanics above
> are proven in code; re-introducing them is a product decision, not an engineering one.
