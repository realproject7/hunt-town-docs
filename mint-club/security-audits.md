# Security & Audits

Because Mint Club holds reserves on behalf of every asset created on it, the protocol's
security is foundational to the whole Hunt Town economy. Co-op project tokens and MT are
reserve-backed through these same contracts.

## Audits

Mint Club V2's contracts have been reviewed through:

- **A professional security audit by CertiK**, completed January 18, 2024. Report:
  [docs.mint.club/audit/report](https://docs.mint.club/audit/report). Mint Club also holds a
  [CertiK KYC Gold Badge](https://www.certik.com/resources/blog/7pSqAsYSLro9gMFeuIjPsj-how-we-do-kyc)
  (highest level) with a live Skynet profile:
  [skynet.certik.com/projects/mint-club](https://skynet.certik.com/projects/mint-club).
- **A community contract audit**: an open, community-run review of the V2 contracts, completed
  December 26, 2023. Recap: [docs.mint.club/audit/com_audit](https://docs.mint.club/audit/com_audit) ·
  reward distribution: [Steemhunt/mint.club-v2-contract #72](https://github.com/Steemhunt/mint.club-v2-contract/issues/72).

Together these provide both an independent professional assessment and a transparent,
community-visible review of the protocol's core contracts.

## Why reserve-backing is a security property

Each asset's reserve is held in its curve and is redeemable by burning, so holders do not
depend on a discretionary treasury or an offchain promise. See
[Bonding Curves](bonding-curves.md).

## The Mint Club V2 contracts

The V2 contracts are the deployed, audited implementation of the create, mint, burn and curve
logic described in this section, and the same contracts the [SDK](sdk.md) drives. Source:
[Steemhunt/mint.club-v2-contract](https://github.com/Steemhunt/mint.club-v2-contract). The
Bond contract on Base, which holds every Base HUNT reserve, is listed in
[Contracts & Addresses](../reference/contracts.md#mint-club-v2).
