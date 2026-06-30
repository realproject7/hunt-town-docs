# Security & Audits

Because Mint Club holds reserves on behalf of every asset created on it, the protocol's
security is foundational to the whole Hunt Town economy — Co-op project tokens and Building
NFTs are reserve-backed through these same contracts.

## Audits

Mint Club V2's contracts have been reviewed through:

- **A professional security audit by CertiK** — an industry third-party audit firm.
- **A community contract audit** — an open, community-run review of the V2 contracts.

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

> **TODO (operator):** link the CertiK report and the community audit recap (both on
> docs.mint.club), and list the audited V2 contract addresses per chain in
> [Contracts & Addresses](../reference/contracts.md).
