# Daily Backing Point (BP)

**Backing Points (BP)** are the Co-op's daily unit of backing power. They determine how much
support a backer can give builders each day, and they are derived entirely from the
[Building NFTs](../hunt/building-nfts.md) a backer holds.

## How BP is issued

- BP is granted **daily** to Building holders.
- The amount scales with the holder's **Mini Building units**, where a **Main Building counts
  as 10 Mini Buildings**:

  ```
  mini_building_units = (main_buildings × 10) + mini_buildings
  ```

- Each day's BP is a fresh allowance — it is meant to be spent that day on backing the
  projects the holder supports.

## How BP is spent

Backers spend BP to **mint project tokens** — directing their daily backing power to the
builders and projects they believe in. Spending BP:

- mints the chosen project's HUNT-backed token, giving the builder demand and liquidity, and
- locks HUNT into that project's bonding-curve reserve.

Backers can also support a project by **donating HUNT directly**, independent of their BP.

## Why BP is tied to Buildings

Linking backing power to Building ownership ties the Co-op's daily activity to HUNT:

- To get more BP, a backer **mints more Buildings**, which **locks more HUNT**.
- More Buildings across the Co-op means more daily BP in circulation, more daily minting,
  and more HUNT locked — the dynamic cycle that grows the Co-op's total value locked and
  strengthens the collective economy.
