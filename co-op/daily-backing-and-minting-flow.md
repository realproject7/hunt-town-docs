# Daily Backing & Minting Flow

The Co-op runs on a **daily loop**. Backing power refreshes each day, backers spend it to
mint the project tokens they support, and every mint locks more HUNT — compounding the
Co-op's locked value over time.

## The loop

1. **Hold Buildings.** Backers hold [Building NFTs](../hunt/building-nfts.md) — Mini
   (Base) and Main (Ethereum). Buildings are the source of backing power.
2. **Receive Daily BP.** Each day, holders receive **Backing Points (BP)** based on the
   Mini Buildings they hold (a Main Building counts as 10 Mini). See
   [Daily Backing Point (BP)](daily-backing-point.md).
3. **Back projects.** Backers spend their daily BP to **mint the project tokens** they want
   to support. They can also **donate HUNT directly** to a project.
4. **HUNT locks.** Each mint routes HUNT into the project's bonding-curve reserve, where it
   is **locked** — raising the Co-op's total value locked and reducing circulating HUNT.
5. **Repeat tomorrow.** BP refreshes the next day, so support is continuous rather than
   one-shot, and projects accrue steady daily backing.

```
hold Buildings ─▶ receive Daily BP ─▶ mint/back projects ─▶ HUNT locks in reserves
       ▲                                                              │
       └──────────────────  refreshes daily  ◀───────────────────────┘
```

## Why a daily cycle

- **Continuous traction for builders.** Projects get backed every day, not just at launch —
  a recurring stream of demand and liquidity.
- **Sustained engagement for backers.** A daily allowance turns backing into a habit, and
  rewards consistent supporters of good projects.
- **Compounding locked value.** Because each day's minting locks more HUNT, the Co-op's TVL
  and HUNT's scarcity grow with sustained activity rather than a single event.

> **TODO (operator):** confirm the exact daily BP issuance per Mini Building and the
> conversion of BP into mint amounts against the live Co-op contracts, and add a worked
> numeric example here.
