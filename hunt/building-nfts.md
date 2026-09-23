# Building NFTs

**Building NFTs lock HUNT.** Each one is minted with HUNT, and that HUNT stays locked behind
the NFT, out of market circulation. They are counted in the locked category on the
[supply](supply.md) page.

There are two tiers:

| Tier | Network | Standard | HUNT to mint | Where the HUNT sits |
| --- | --- | --- | --- | --- |
| **Main Building** | Ethereum mainnet | ERC-721 | 1,000 HUNT | The Town Hall contract, which records when it unlocks |
| **Mini Building** | Base | ERC-1155 (token id `0`) | 100 HUNT | The reserve of the Mint Club V2 Bond contract on Base |

## How the locking works

- **Main Buildings** are minted from HUNT through the Town Hall. The Town Hall holds the
  1,000 HUNT behind each Main Building and records its unlock time. Once a Building has
  unlocked, burning it releases the HUNT.
- **Mini Buildings** are minted through the Mint Club V2 Bond on Base, which holds the HUNT
  behind them in its reserve alongside every other Base HUNT reserve.
- Minting more Buildings locks more HUNT, which is why Building supply appears directly in
  the supply accounting: 1,000 HUNT per Main Building on Ethereum, and the Mint Club Base
  balance on Base.

## Contracts

| Building | Network | Address |
| --- | --- | --- |
| Main Building NFT | Ethereum mainnet | `0x0c9Bb1ffF512a5B4F01aCA6ad964Ec6D7fC60c96` |
| Mini Building NFT | Base | `0x475f8E3eE5457f7B4AAca7E989D35418657AdF2a` |

The Town Hall and Building contracts were audited by BEOSIN (completed December 6, 2022) —
[announcement](https://news.hunt.town/p/hunt-town-security-audit-is-completed) ·
[report (PDF)](https://beosin.com/audits/Hunt-Town_202212051700.pdf). See
[Links & Resources → Security & Audits](../reference/links.md) for the full audit list.

---

## Under consideration: Building NFT credits for h402

> **Status: proposed.** The mechanic below was implemented and tested in the h402 codebase,
> then pulled from the launch MVP. It is documented here as a **future addition under
> review**, not a live feature.

A natural way to connect Building NFTs to the studio's newest product is to let Buildings
**fund agent payments on [h402](../h402/overview.md)**. The idea: Building holders receive
a **recurring h402 credit** — a stablecoin-denominated allowance, usable to pay for h402
calls — simply for holding Buildings. It would give Building NFTs a recurring use on the
agent capability market.

The prototype worked as follows.

### Credit amounts

Credits are denominated in micro-USD and scale with Building holdings:

| Holding | Mini units | Weekly credit |
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
delegate) calls a paid capability, available credit is **drawn down before any USDC is
charged**. Only the remainder, if any, settles as a normal Base USDC payment. See
[How Paying Works](../h402/how-paying-works.md) for the underlying x402 flow.

> **Why it's under review:** the program was removed from the h402 launch MVP (replaced by
> a simpler bonus-credit mechanism) to keep the initial release lean. The mechanics above
> are proven in code; re-introducing them is a product decision, not an engineering one.
