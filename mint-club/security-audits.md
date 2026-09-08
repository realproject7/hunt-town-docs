# Security & Audits

Because Mint Club holds reserves on behalf of every asset created on it, the protocol's
security is foundational to the whole Hunt Town economy — Co-op project tokens and Building
NFTs are reserve-backed through these same contracts.

## Audits

Mint Club V2's contracts have been reviewed through:

- **A professional security audit by CertiK** — completed January 18, 2024. Report:
  [docs.mint.club/audit/report](https://docs.mint.club/audit/report). Mint Club also holds a
  [CertiK KYC Gold Badge](https://www.certik.com/resources/blog/7pSqAsYSLro9gMFeuIjPsj-how-we-do-kyc)
  (highest level) with a live Skynet profile:
  [skynet.certik.com/projects/mint-club](https://skynet.certik.com/projects/mint-club).
- **A community contract audit** — an open, community-run review of the V2 contracts, completed
  December 26, 2023: [Steemhunt/dixel-v2-contract #28](https://github.com/Steemhunt/dixel-v2-contract/issues/28).

Together these provide both an independent professional assessment and a transparent,
community-visible review of the protocol's core contracts.

## Why reserve-backing is a security property

The bonding-curve model is not only an economic design; it is also a safety property. Because
each asset's value is held as **reserve in its curve** and is **redeemable by burning**,
holders are not dependent on a discretionary treasury or an off-chain promise — the backing is
on-chain and rule-bound by the curve contract.

## The Mint Club V2 contracts

The V2 contracts are the deployed, audited implementation of the create / mint / burn / curve
logic described throughout this section, and the same contracts the [SDK](sdk.md) drives.
