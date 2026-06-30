# Create Assets

Mint Club lets anyone deploy a bonding-curve asset **with no code**. You choose what to
create, the curve that governs its price, and the reserve token that backs it, then deploy.

## Two asset types

| Type | Standard | Typical use |
| --- | --- | --- |
| **Token** | ERC-20 | Project tokens, community tokens, memecoins, platform tokens |
| **NFT** | ERC-1155 | Memberships, collectibles, trading cards, proof-of-attendance |

Both are issued on a bonding curve, so both are reserve-backed, instantly mintable, and
burnable.

## What a creator configures

When creating an asset, a creator sets:

- **Name / ticker / metadata** — including logo and website (see
  [Creator Tools](creator-tools.md)).
- **Reserve token** — the asset that backs the curve. In the Hunt Town economy this is
  often **HUNT**, making the asset HUNT-backed; Mint Club supports other reserve tokens too.
- **Curve type and intervals** — linear, exponential, or flat, with tunable price steps
  (see [Bonding Curves](bonding-curves.md)).
- **Supply parameters** — including maximum supply where applicable (e.g. NFT collections
  with a capped edition count).

Once deployed, the asset is live and tradable on its curve immediately — no liquidity pool
to seed, no listing step.

## No-code, but composable

The no-code creator flow is the front door, but the resulting assets are standard ERC-20 /
ERC-1155 tokens on open contracts. That is why external teams have repeatedly built whole
products on top of Mint Club assets (Farcards, Memberify, Hamcaster, and others in the
[Build Log](../track-record/build-log.md)), and why the [SDK](sdk.md) can drive the same
creation and trading flows programmatically.

> **TODO (operator):** list the exact networks/chains Mint Club create supports today, and
> any creation requirements or fees, verified against the live app.
