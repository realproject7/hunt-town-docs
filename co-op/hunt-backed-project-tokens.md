# HUNT-backed Project Tokens

Every token launched in the Co-op is a **HUNT-backed project token**: a child token issued
on bonding-curve mechanics with **HUNT held in its reserve**. This is what makes the Co-op a
shared economy rather than a collection of unrelated launches.

## What "HUNT-backed" means

- The token is minted against a **bonding-curve reserve** denominated in HUNT.
- **Minting** the token routes HUNT into that reserve and locks it. **Burning** (selling)
  returns HUNT from the reserve.
- The token's price is a function of its supply along the curve, not of an externally seeded
  liquidity pool, so there is always a reserve actually backing it.

## One reserve, many projects

Each builder runs a **completely independent project** with its own token, curve, and
reserve. Because every reserve is HUNT, the projects are still linked. When project tokens
grow in market activity, more HUNT locks inside their bonding-curve pools: less circulating
HUNT, and a larger total value locked across the Co-op.

On a traditional launchpad, each new token competes with the last for liquidity and
attention. In the Co-op, each new token **adds** to a common reserve that backs them all.

See [HUNT as the Reserve Token](../hunt/reserve-token.md) for the economy-wide view of this
mechanism, and [Mint Club](../mint-club/overview.md) for the bonding-curve protocol that
makes reserve-backed issuance possible.
