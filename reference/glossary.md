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
the outcome, not the vendor.

**Child token**: a token issued on a bonding curve with another token (often HUNT) as its
reserve. Co-op project tokens and MT (Mint Token) are HUNT-backed child tokens.

**Co-op**: Hunt Town's HUNT-backed launchpad and DEX, where builders launch tokens with HUNT
as their reserve and anyone can trade them against HUNT. Lives at coop.hunt.town.

**EIP-3009**: the standard for signed token-transfer authorizations. h402 uses it so a caller
signs a stablecoin payment locally.

**Factory NFT**: Hunt Town's HUNT-backed NFT on Ethereum (ERC-1155, token id `0`). It mints
at NAV and burns for 95% of NAV in HUNT. See [Factory NFT](../factory-nft/overview.md).

**h402**: Hunt Town's Agent Capability Market Layer: the x402 capability store where agents
discover, compare, and pay per call for capabilities. See [h402](../h402/overview.md).

**HUNT**: the ERC-20 token that backs the Factory NFT and serves as the reserve asset for
Co-op project tokens and other HUNT-backed tokens. Non-inflationary: no address can mint it.

**lpTOKEN**: an ERC-20 share of a Uniswap v4 liquidity position held by an lpTOKEN.fun
vault; a pro-rata claim on that position, its accrued fees, and the vault's idle balances.

**Marketplace royalty**: the 3% royalty (ERC-2981) set on Factory NFT sales. Marketplaces
that honor it pay it to a royalty operator, which buys HUNT with it and deposits that HUNT
into the vault.

**Mint / Burn**: buying (mint) and selling (burn) an asset against its bonding curve. Factory
NFTs work differently: they mint at NAV and burn for 95% of NAV, with no curve.

**Mint Club**: the no-code bonding-curve protocol for tokens (ERC-20) and NFTs (ERC-1155).
Co-op project tokens and MT are issued on it.

**MT (Mint Token)**: Mint Club's platform token; itself a HUNT-backed child token. It replaced
the older MINT token on June 5, 2025.

**NAV per NFT**: the HUNT held by the Factory NFT contract divided by the number of Factory
NFTs. Minting one NFT locks this much HUNT. It was 1,000 HUNT at launch, and it rises when
HUNT is added outside a mint or when NFTs are burned. See [The NAV Vault](../factory-nft/nav-vault.md).

**Provider**: one concrete implementation of a capability on h402, with its own input
schema, price, upstream service, and a stored real-response sample. Every call is pinned to
exactly one provider.

**Reserve token**: the asset held in a bonding curve to back an issued token/NFT. In Hunt
Town this is frequently HUNT.

**Seed NFT**: the one Factory NFT minted when the contract was deployed, backed by 1,000
HUNT. The team holds it, and it has no special rights. See
[The NAV Vault](../factory-nft/nav-vault.md).

**Top-up**: the HUNT a holder adds when migrating Buildings, so that their value reaches
whole Factory NFTs. It is never refunded. See
[Migrating Buildings](../factory-nft/migrating-buildings.md).

**x402**: the standard that uses HTTP `402 Payment Required` as a real payment handshake;
h402's foundation.

## Legacy

**Building NFT**: Hunt Town's earlier HUNT-backed NFTs. A **Main Building** (Ethereum,
ERC-721) holds 1,000 HUNT in the Town Hall contract, released when the Building is burned
after it unlocks. A **Mini Building** (Base, ERC-1155) was minted with 100 HUNT through Mint
Club. Holders can migrate them into Factory NFTs. See
[Migrating Buildings](../factory-nft/migrating-buildings.md).

**Town Hall**: the Ethereum contract that holds the 1,000 HUNT behind each Main Building and
records when each one unlocks. See [Migrating Buildings](../factory-nft/migrating-buildings.md).
