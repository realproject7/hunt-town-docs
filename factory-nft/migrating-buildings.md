# Migrating Buildings

Building NFTs are Hunt Town's legacy NFTs. Holders can turn them into Factory NFTs. Each
Building counts toward the lock-up at a fixed HUNT value, and you add HUNT to reach whole
Factory NFTs.

## The rules

- **One way.** Migrated Buildings do not come back.
- **One chain at a time.** Main Buildings migrate on Ethereum. Mini Buildings migrate on
  Base. Each migration is separate.
- **You choose how many.** Pick how many of your Buildings to use each time.
- **Whole NFTs only.** There are no partial Factory NFTs and no refunds.
- **Factory NFTs arrive on Ethereum,** whichever chain you migrate from.

| | Main Building | Mini Building |
| --- | --- | --- |
| **Network** | Ethereum | Base |
| **Standard** | ERC-721 | ERC-1155, token id `0` |
| **Counts as** | 1,000 HUNT each | 100 HUNT each |
| **Top-up paid in** | HUNT on Ethereum | HUNT on Base |
| **Factory NFTs arrive on** | Ethereum | Ethereum |

## Counted in full

The migration takes each Building at the HUNT it was minted with and waives what would
normally hold that HUNT back.

- **Locked Main Buildings count.** Main Buildings still locked in the Town Hall are accepted
  at the full 1,000 HUNT. You do not wait for the unlock date.
- **No 5% off Mini Buildings.** Each Mini Building counts as the full 100 HUNT it was minted
  with. The 5% burn royalty that applies when a Mini Building is burned on Mint Club is not
  taken off.

## Your statement

On hunt.town you type how many Buildings to send, or tap Max. For Main Buildings you can
also choose which ids go through. Before you confirm, you see a statement for that number:

```
Building value = Buildings × 1,000 HUNT (Main) or × 100 HUNT (Mini)
Factory NFTs   = Building value ÷ lock-up per NFT, rounded up
Top-up         = Factory NFTs × lock-up per NFT − Building value
```

The lock-up per NFT is the HUNT one Factory NFT locks on Ethereum right now: 1,000 HUNT × the
multiplier. Because the count rounds up to whole NFTs, the top-up is never negative: you may
add HUNT, but you never get any back. Pick the number of Buildings that gives the top-up you
want.

## Worked example

With a lock-up of 1,050 HUNT per NFT (a multiplier of ×1.0500):

| You send | Building value | You get | Top-up |
| --- | --- | --- | --- |
| 12 Mini Buildings | 1,200 HUNT | 2 Factory NFTs | 900 HUNT |
| 10 Mini Buildings | 1,000 HUNT | 1 Factory NFT | 50 HUNT |

At launch the multiplier is ×1.0000, so one Main Building or ten Mini Buildings convert to
one Factory NFT with no top-up. The top-up grows as the multiplier rises.

## Where to migrate

Migrate at [hunt.town/migrate](https://hunt.town/migrate). The top-up is paid in HUNT on
the same chain as your Buildings: HUNT on Ethereum for Main Buildings, and Base HUNT for
Mini Buildings. See [Base HUNT (Bridged)](../hunt/base-hunt.md).

## Legacy Buildings

Before the Factory NFT, Hunt Town's NFTs were Buildings. Each one was minted with HUNT, and
that HUNT stayed behind it.

- A **Main Building** (Ethereum, ERC-721) was minted with 1,000 HUNT through the Town Hall
  contract. The Town Hall holds that HUNT and records when each Building unlocks. Once a
  Building has unlocked, burning it releases the HUNT.
- A **Mini Building** (Base, ERC-1155) was minted with 100 HUNT through the Mint Club V2
  Bond on Base, which holds that HUNT in its reserve.

As of September 23, 2026, there are 1,355 Main Buildings and 11,241 Mini Buildings.

Look them up: [Main Building collection](https://opensea.io/collection/hunt-town) ·
[Mini Building on Mint Club](https://mint.club/nft/base/MINIBD).

### Legacy contracts

| Contract | Network | Address |
| --- | --- | --- |
| Main Building NFT (ERC-721) | Ethereum | `0x0c9Bb1ffF512a5B4F01aCA6ad964Ec6D7fC60c96` |
| Mini Building NFT (ERC-1155, id `0`) | Base | `0x475f8E3eE5457f7B4AAca7E989D35418657AdF2a` |
| Town Hall (holds the HUNT behind Main Buildings) | Ethereum | `0xb09A1410cF4C49F92482F5cd2CbF19b638907193` |

The Town Hall and Building contracts were audited by BEOSIN (completed December 6, 2022):
[announcement](https://news.hunt.town/p/hunt-town-security-audit-is-completed) ·
[report (PDF)](https://beosin.com/audits/Hunt-Town_202212051700.pdf). See
[Links & Resources](../reference/links.md) for the full audit list.
