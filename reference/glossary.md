# Glossary

**Agent**: autonomous software that performs economic actions onchain (calling services,
paying for capabilities) without a human in the loop. The "Agent" half of the Builder & Agent
Economy, and the primary user of [h402](../h402/overview.md).

**Bonding curve**: a contract that sets an asset's price as a deterministic function of its
supply, backed by a reserve. Minting raises price and adds reserve; burning lowers price and
returns reserve. The core primitive of [Mint Club](../mint-club/bonding-curves.md).

**Builder**: a creator who launches tokens and projects on Hunt Town's primitives. The
"Builder" half of the Builder & Agent Economy.

**Burn fee**: the 5% of NAV that stays in the vault when a Factory NFT is burned. It raises
the NAV per NFT for everyone still holding. See [Mint & Burn](../factory-nft/mint-and-burn.md).

**Capability**: one task on h402, named `category/action` (e.g. `web/search`). It describes
the outcome, not the vendor. ("Route" is the internal term for the same thing.)

**Child token**: a token issued on a bonding curve with another token (often HUNT) as its
reserve. Co-op project tokens and MINT (MT) are HUNT-backed child tokens.

**Co-op**: Hunt Town's HUNT-based launchpad and DEX, where builders launch HUNT-backed tokens
and anyone can trade them against HUNT. Lives at coop.hunt.town.

**EIP-3009**: the `transferWithAuthorization` standard used by h402 to sign a stablecoin
payment authorization locally, enabling non-custodial settlement.

**Factory NFT**: Hunt Town's HUNT-backed NFT on Ethereum (ERC-1155, token id `0`). It mints
at NAV and burns for 95% of NAV in HUNT. See [Factory NFT](../factory-nft/overview.md).

**h402**: Hunt Town's Agent Capability Market Layer: the x402 capability store where agents
discover, compare, and pay per call for capabilities. See [h402](../h402/overview.md).

**HUNT**: the ERC-20 token that backs the Factory NFT and serves as the reserve asset for
Co-op project tokens and other HUNT-backed tokens. Non-inflationary: no address can mint it.

**Lock-up per NFT**: the HUNT one mint locks in the Factory NFT vault: the current NAV per
NFT, or 1,000 HUNT × the multiplier. It was 1,000 HUNT at launch. See
[Mint & Burn](../factory-nft/mint-and-burn.md).

**lpTOKEN**: an ERC-20 share of a Uniswap v4 liquidity position held by an lpTOKEN.fun
vault; a pro-rata claim on that position, its accrued fees, and the vault's idle balances.

**Marketplace royalty**: the 3% royalty (ERC-2981) set on Factory NFT sales. Marketplaces
that honor it pay it to a royalty operator, which buys HUNT with it and deposits that HUNT
into the vault.

**Mint / Burn**: buying (mint) and selling (burn) an asset against its bonding curve. Factory
NFTs work differently: they mint at NAV and burn for 95% of NAV, with no curve.

**MINT (MT)**: Mint Club's platform token; itself a HUNT-backed child token. (Migrated from
the older "MINT" token to "MT" on June 5, 2025.)

**Mint Club**: the no-code bonding-curve protocol for tokens (ERC-20) and NFTs (ERC-1155)
that powers much of the ecosystem.

**Multiplier**: the NAV per NFT divided by 1,000 HUNT, shown as ×1.0000. It was ×1.0000 at
launch. It rises when HUNT is added without minting, and when NFTs are burned.

**NAV per NFT**: the HUNT held by the Factory NFT contract divided by the number of Factory
NFTs, rounded down. See [The NAV Vault](../factory-nft/nav-vault.md).

**Provider**: one concrete implementation of a capability on h402, with its own input
schema, price, upstream service, and a stored real-response sample. Every call is pinned to
exactly one provider.

**Reserve token**: the asset held in a bonding curve to back an issued token/NFT. In Hunt
Town this is frequently HUNT.

**x402**: the standard that uses HTTP `402 Payment Required` as a real payment handshake;
h402's foundation.

## Legacy

**Building NFT**: Hunt Town's earlier HUNT-backed NFTs. A **Main Building** (Ethereum,
ERC-721) holds 1,000 HUNT in the Town Hall contract until it unlocks; a **Mini Building**
(Base, ERC-1155) was minted with 100 HUNT through Mint Club. Holders can migrate both into
Factory NFTs. See [Migrating Buildings](../factory-nft/migrating-buildings.md).
