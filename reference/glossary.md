# Glossary

**Agent** — autonomous software that performs economic actions onchain (calling services,
paying for capabilities) without a human in the loop. The "Agent" half of the Builder & Agent
Economy; the primary user of [h402](../h402/overview.md).

**Backer** — a Co-op participant who supports builders by minting their project tokens daily
(with BP) or donating HUNT directly.

**Backing Point (BP)** — the Co-op's daily unit of backing power, issued to Building NFT holders
based on their Mini Building units and spent to mint project tokens.

**Bonding curve** — a contract that sets an asset's price as a deterministic function of its
supply, backed by a reserve. Minting raises price and adds reserve; burning lowers price and
returns reserve. The core primitive of [Mint Club](../mint-club/bonding-curves.md).

**Builder** — a creator who launches tokens and projects on Hunt Town's primitives. The
"Builder" half of the Builder & Agent Economy.

**Building NFT** — Hunt Town's membership/backing-power asset, backed by HUNT. **Main Building**
(Ethereum, ERC-721, 1,000 HUNT) and **Mini Building** (Base, ERC-1155, 100 HUNT); 1 Main = 10
Mini.

**Child token** — a token issued on a bonding curve with another token (often HUNT) as its
reserve. Co-op project tokens and MINT (MT) are HUNT-backed child tokens.

**Co-op** — Hunt Town's onchain cooperative, where builders launch HUNT-backed tokens and backers
mint them daily. Moving to coop.hunt.town.

**EIP-3009** — the `transferWithAuthorization` standard used by h402 to sign a stablecoin payment
authorization locally, enabling non-custodial settlement.

**h402** — Hunt Town's Agent Capability Market Layer: the x402 capability store where agents
discover, compare, and pay per call for capabilities. See [h402](../h402/overview.md).

**HUNT** — the ERC-20 reserve asset that backs and connects every token and NFT in the Hunt Town
economy. Non-inflationary; value accrues through locking.

**Mint / Burn** — buying (mint) and selling (burn) an asset against its bonding curve.

**MINT (MT)** — Mint Club's platform token; itself a HUNT-backed child token. (Migrated from the
older "MINT" token to "MT" on June 5, 2025.)

**Mint Club** — the no-code bonding-curve protocol for tokens (ERC-20) and NFTs (ERC-1155) that
powers much of the ecosystem.

**Reserve token** — the asset held in a bonding curve to back an issued token/NFT. In Hunt Town
this is frequently HUNT.

**Capability** — one task on h402, named `category/action` (e.g. `web/search`). It describes
the outcome, not the vendor. ("Route" is the internal term for the same thing.)

**Provider** — one concrete implementation of a capability on h402, with its own input
schema, price, upstream service, and a stored real-response sample. Every call is pinned to
exactly one provider.

**lpTOKEN** — an ERC-20 share of a Uniswap v4 liquidity position held by an lpTOKEN.fun
vault; a pro-rata claim on that position, its accrued fees, and the vault's idle balances.

**x402** — the standard that uses HTTP `402 Payment Required` as a real payment handshake;
h402's foundation.
