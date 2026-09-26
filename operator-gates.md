# Operator Gates

> **Not published.** This file is intentionally left out of `SUMMARY.md`, so GitBook ignores
> it on import.
>
> **The published docs contain zero `TODO (operator)` callouts.** Every page reads as final
> copy. This file is the *only* record of what is still unverified, undecided, or
> deliberately omitted, so it must be read before the docs are treated as final. Each item is
> either "add detail later" or "a decision only the operator can make."

---

## A. Decisions only the operator can make

These are not missing facts. They are editorial, business, or legal calls.

- [ ] **Factory launch and publish timing.** The Factory NFT group, the Buyback & Burn
  rewrite, the new supply method, Terms §6, and the links to `hunt.town/factory`,
  `hunt.town/migrate` and `hunt.town/hunt` all describe the state after launch. Those site
  routes do not resolve until the new site ships (hunt.town still serves the Co-op app), and
  the contracts are not deployed yet. Publish the docs
  together with the Factory launch, not before. Merging the docs PR publishes everything at
  once. (Since 2026-09-24 `hunt.town/hunt` is a 307 redirect to `hunt.town/factory#hunt` in
  town-web-2; the docs link the new location.)
- [ ] **Co-op publish timing.** The Co-op pages, the glossary, Terms and the HUNT pages
  describe Co-op after the daily BP, voting, airdrop-claim and donation removal
  (2026-09-23). The live app still runs those mechanics. Decide whether to publish with the
  new Co-op release or before it. Merging the docs PR publishes everything at once.
- [ ] **Terms: legal sign-off, including the Factory section.** The 2026-09-23 Factory edits:
  §1 (Onchain Product Factory; the Factory NFT replaces Building NFTs in the product list), §2
  (the blanket no-responsibility line is now scoped to user-created projects, with a
  pointer to §6), §5 (HUNT backs the Factory NFT; a mint deposits HUNT, a burn releases 95%
  of NAV), §6 (rewritten for Factory NFTs: HUNT-denominated redemption, 5% burn fee, 3%
  royalty, inflows not guaranteed, owner powers and limits, one-way migration, not an
  investment), §8 (scoped to Mint Club-based products), and §11 (three Factory risks). Also
  still open from earlier: §1 says the products connect "builders, holders, and AI agents"
  (was "backers"), "backing or minting" became "buying or minting", and whether
  **lpTOKEN.fun needs its own clause** (a live product with LP, fee, and permanent-lock
  mechanics). The date line now reads September 23, 2026: set it to the real publish date.
  §13 keeps the standard "loss of assets, data, or profits" wording (legal text, not copy).
- [ ] **Terms §9 (h402 Payments) contradicts the h402 docs.** §9 says payments go "directly
  from your wallet to a provider's settlement address through smart contracts" and that the
  Core Team "does not hold, route, or reverse user funds." `h402/how-paying-works.md` and
  `h402/for-builders.md` say callers pay h402's treasury, which then pays the provider. A
  live 402 check in the audit (2026-09-23) showed the same payee for two different
  `web/search` providers. §9 was left unchanged on purpose. Legal and business call: rewrite
  §9 for the two-hop flow, or change the flow.
- [ ] **Whether the docs name the products behind revenue.** Every page says "revenue from
  Hunt Town's products" and names no product as a revenue source, matching the site. Decide
  whether the docs should name them.
- [ ] **MT buyback funding vs product revenue feeding the NAV: operator decision pending.**
  `mint-club/mint-token.md` and `mint-club/economics.md` still say platform revenue funds the
  MT buyback and burn. That text was left as it is.
- [ ] **Replacing the whitepaper PDF.** `hunt.town/HUNT-Whitepaper.pdf` is the Co-op-era paper
  (dated 18/12/2025: "builders and backers", daily Backing Points). town-web-2 ships the same
  file, so it survives the launch, and the site nav still links it. `reference/links.md`
  now links docs.hunt.town instead. Decide: replace the PDF with an export of these docs at
  launch, or drop it.
- [ ] **Old docs URLs without a clear successor.** `.gitbook.yaml` now redirects 9 old paths
  (see the 2026-09-23 Factory note). Five paths in the live sitemap have no clear target and
  will 404 at launch: `/information`, `/to-do-list`, `/how/builders-and-backers`,
  `/how/daily-backing-and-minting-flow`, `/how/daily-backing-point-bp`. Decide: add
  site-level redirects (for example to the Introduction or the Co-op overview) or let them
  404.

Resolved on 2026-09-23:

- [x] **Building NFT → h402 credits: cut.** The section left with `hunt/building-nfts.md`, and
  the references in `h402/mount.md` and `h402/how-paying-works.md` are gone.
- [x] **Co-op domain.** coop.hunt.town already serves the app (HTTP 200, audit 2026-09-23).
  "(moving)" is gone from `reference/links.md`, the glossary, and `co-op/overview.md`.

## B. Deliberately omitted: do not publish until verified

- [ ] **Factory contract addresses.** FactoryNFT, FactoryZapRouter and the migrators are not
  deployed. Add them only after deployment: a Factory NFT section in
  `reference/contracts.md`, a contract row in `factory-nft/overview.md`, and explorer links
  in `reference/links.md`. At the same time, re-check every Factory fact against the deployed
  contracts. The pages follow the draft at `Steemhunt/hunt-town#12`, commit `2194eb5`.
- [ ] **Factory NFT on OpenSea.** The site builds its link from the contract address:
  `opensea.io/item/ethereum/<FactoryNFT>/0` (one token id). Add the same link to
  `factory-nft/overview.md` and `reference/links.md` with the addresses.
- [ ] **Royalty operator wallet.** Never publish it (a team wallet). The docs describe the
  role only.
- [ ] **Migration mechanics.** No migrator contract exists yet. The docs state the rules: one
  way, per chain, 1,000 HUNT per Main and 100 HUNT per Mini, the statement math, locked Main
  Buildings accepted, Factory NFTs delivered on Ethereum. They do not say what happens to a
  migrated Building and its HUNT, which approvals are needed, whether a max top-up guard
  exists, or how long a Base migration takes to arrive on Ethereum. Add these once the
  migrator is final. (The site assumes a guard: it sends the statement's top-up plus up to
  0.5% of the NFTs' lock-up, capped by the HUNT approval. Document it only if the migrator
  takes a max top-up.)
- [ ] **h402 treasury / operating wallet addresses.** Decide whether these should be public
  at all. Currently not listed. The treasury is already visible as the payee in every `402`
  challenge and in the public ARD entries, so listing it would not reveal anything new.

## C. Detail to add when available

Each of these has a page that reads fine today; the gate is extra specificity.

| What | Page |
| --- | --- |
| Refresh at publish: legacy supply (1,355 Main, 11,241 Mini as of 2026-09-23) | `factory-nft/migrating-buildings.md` |
| Refresh at publish: the Mini Building reserve (1,124,100 HUNT) and the ~2.48M HUNT launch shift, both as of 2026-09-23 | `hunt/supply.md` |
| Concrete launch steps, requirements/fees, live launch link | `co-op/launch-a-project-token.md` |
| Mint Club: supported chains, creator-tool parameter ranges, SDK package name | `mint-club/create.md`, `creator-tools.md`, `sdk.md` |
| MINT (MT) address, networks, supply, buyback parameters; any live MT reward program (the "daily rewards" line was dropped because its known example, MintDrop, is Sunset) | `mint-club/mint-token.md` |
| Mint Club V2 audited contract addresses per chain | `mint-club/security-audits.md`, `reference/contracts.md` |
| h402: Builders submission form URL, package README links | `h402/for-builders.md`, `packages.md` |
| Official social links (X, Farcaster, Discord, Telegram) | `reference/links.md` |
| Build Log: the em dashes are gone from the entry bodies (fixed in the site and mirrored here, 2026-09-24). 5 "studio" mentions (#015, #012, #010, #003) stay verbatim with town-web-2 `build-log.ts`. The dead Foundation link in #018 (`build-log.ts` L706) also stays. Fix them in the site first, then regenerate the page. | `track-record/build-log.md` |

---

## Sync notes

### 2026-09-25: site design QA 1 to 5

Sources: the unreleased town-web-2 Factory branch, the contract draft at
`Steemhunt/hunt-town#12` `2194eb5` (unchanged since 2026-09-23), and the site's supply code.
Every Factory and HUNT address in the docs matches the site's contract config; the contract
claims (rounding, 95% burn, burn only your own, supply floor, owner powers, validator scope,
zap refund and deadline) were re-read in the source.

- **Lock-up, not price.** "Minting one NFT then costs" became "locks" (Overview). The Overview
  intro now says you lock HUNT to mint, the four sources add HUNT, and a burn takes 95% back;
  "At a glance" gains Lock-up per NFT and Pay with. The glossary adds **Lock-up per NFT**.
- **Mint & Burn:** the hunt.town allowance for a swap mint (0.5% NAV + 1% swap, the
  transaction must land within 20 minutes) and the site's burn breakdown (1,000 HUNT × the
  multiplier × NFTs, less 5%).
- **Migrating Buildings:** the two waivers are their own section, "Counted in full", as on
  the site; the statement section says you type a count or tap Max, and pick ids for Main
  Buildings.
- **HUNT (ERC20):** the core-asset paragraph names all the inflows and uses lock-up wording.
  **Supply** and **The NAV Vault** link the live sections (`#supply`, `#vault`).
- **HUNT as the Reserve Token:** "Shared upside" and "A real floor" read as price claims;
  they are now "A shared foundation" and "HUNT behind every token".
- **Independent fact check (2026-09-25)** of the Factory NFT and HUNT pages against the
  contract source, the site code and the plan: no numeric or formula errors; 11 wording
  findings, 10 fixed. The mint maximum is a HUNT cap only for HUNT mints (a swap mint caps
  its input token); the owner can also transfer or renounce ownership (Ownable2Step); the
  royalty is set by ERC-2981 and paid by marketplaces that honor it; an approval can move
  NFTs but not burn them from the owner's wallet; "any HUNT sent raises NAV" now excludes
  mints (and the glossary's multiplier line says burns raise it too); Buildings "hold" HUNT
  rather than "lock" it (their HUNT counts as circulating); the 88 HUNT reconciliation has
  no record; the canonical bridge is the L1/L2 Standard Bridge pair; "locked for as long as
  the token exists" no longer contradicts selling. Left for the migrator: the top-up guard.
  Not verifiable from local sources: HUNT token history dates, Town Hall burn behaviour, the
  Mini Building royalty rate, external links (all carried from the 2026-09-23 audit).

### 2026-09-23: Factory rework

Sources: the Factory rework plan (v3) and an internal docs audit (99 findings), the lead's
contract draft (`Steemhunt/hunt-town#12` at `2194eb5`), and town-web-2 `origin/main` at
`86f82a2`. The pre-rework tree is backed up locally.

- **Identity: Hunt Town is an Onchain Product Factory** (renamed from "Web3 Product Factory" on 2026-09-24). "Studio" is gone from every published
  page except the Build Log entry bodies (gate C).
- **40 pages became 43.** New group `## Factory NFT` after Hunt Town:
  `factory-nft/overview.md`, `mint-and-burn.md`, `nav-vault.md`, `migrating-buildings.md`.
  `hunt-town/studio-model.md` is now `hunt-town/factory-model.md` ("The Factory Model").
  `hunt/building-nfts.md` was removed: its legacy facts, contracts, and the BEOSIN audit
  moved to `migrating-buildings.md`, and the h402 credits proposal was cut.
- **Factory NFT facts** follow the plan §2 and §3 and the contract draft: Ethereum, ERC-1155
  id 0, unlimited supply, non-upgradeable; the contract holds the HUNT; a seed of one NFT at
  1,000 HUNT held by the team; minimum supply one; mint = V × q ÷ N, rounded up; burn = 95%
  of NAV, rounded down, and the 5% stays; multiplier = NAV per NFT ÷ 1,000; any HUNT sent in
  raises NAV with no claim or holding period; a 3% royalty to a royalty operator that buys
  HUNT; the owner can change only metadata, royalty operator and transfer validator, and the
  validator never applies to mint or burn; zap with ETH, USDC or USDT through Uniswap V4; the
  bulk vs separate burn example from the draft README; holder math 0.95 × m_burn ÷ m_mint,
  break-even above +5.26%. No deposit schedule is stated. "Other income" is listed and never
  described. No product is named as a revenue source.
- **Buyback & Burn** is now the historical record, with the same file, title, and "The
  historical record" heading. The full 16-row ledger (date, event, HUNT, USD at execution,
  record) was generated from town-web-2 `src/content/hunt-buybacks.ts`. The 88 HUNT
  reconciliation row is unlinked, because its old link pointed at the retired docs page.
  The page says burns ended and product revenue now buys HUNT for the Factory NFT.
- **Supply** follows the plan §4 ruling: Buildings leave the locked category. Locked on
  Ethereum = FactoryNFT HUNT balance + Neverlose.money vault. Locked on Base = Mint Club V2
  Bond HUNT balance minus the Mini Building reserve (`tokenBond(miniBuilding)`, 1,124,100
  HUNT on 2026-09-23). The `hunt.town/about` link is gone, and live figures point at
  `hunt.town/factory`.
- **"No minting function" corrected** on HUNT (ERC20), Supply, and Buyback & Burn: the
  contract has a minter role, its only minter was removed on 2024-02-19, so no address can
  mint. "Launched 2018" now notes that the ERC-20 contract dates from February 2019.
- **Terms:** §1, §2, §5, §6, §8, §11 and the date line changed (gate A). §9 is unchanged
  (gate A).
- **Reference:** Factory terms added to the glossary (re-sorted A to Z, Buildings under
  "Legacy"). Contracts: Buildings under "Legacy", `0xb09A…7193` relabelled as the Town Hall,
  and the Mint Club V2 Bond on Base added. Links: "Website", a docs link instead of the
  Co-op-era PDF, a Co-op link, an Ethereum HUNT route, price, supply and burn record split
  into three links, and legacy labels.
- **Other stale facts fixed:** the Mint Club fee rule (protocol fee = 20% of the creator
  royalty, deducted on claim; royalty 0% to 50%; per-chain creation fee) on Economics and
  Mint & Burn. The MT page drops the fee-unit and daily-rewards claims and the "consistent
  buy pressure" line; the MT buyback text itself is unchanged (gate A). The Mint Club
  community audit now links the V2 recap and `mint.club-v2-contract #72` (it pointed at the
  2022 Dixel audit). Mini vs Main Buildings on the Mint Club pages. Co-op lives at
  coop.hunt.town. The README says "four active products run today". The h402 builders
  endpoint is "reachable over HTTP". The Base HUNT users are the Co-op and Mint Club.
- **Redirects** added to `.gitbook.yaml` (syntax checked against GitBook's content
  configuration docs on 2026-09-23): `hunt-town/studio-model`, `hunt/building-nfts`,
  `token/building-nfts`, `token/hunt`, `token/hunt-backed-project-tokens`,
  `how/launch-a-project-token`, `how/hunt-as-the-reserve-token`, `ecosystem/mint-club`,
  `ecosystem/basehunt`. Page slugs follow file names in Git Sync (checked in the PR #1
  preview sitemap), so the new pages publish at `/factory-nft/<file>`.
- **Em dashes** swept from every page except the Build Log entry bodies (gate C).
- **Not verified, left as is** (the audit's "Not verified" list): lpTOKEN contract
  internals, h402 facilitator and rail details, the CoinGecko and Dune links, Terms §8 "no
  administrative control over Mint Club", Build Log metrics, and the Mint Club creator-tool
  and SDK feature lists.

### 2026-09-23: Co-op pivot, HUNT re-sync, lpTOKEN chains, h402 beta

- **Co-op is now a HUNT-based launchpad and DEX.** Per the operator, the daily Backing
  Points → voting → airdrop-claim loop and HUNT donations (with the Donors leaderboard) are
  gone from the docs. Deleted: `co-op/daily-backing-point.md`,
  `co-op/daily-backing-and-minting-flow.md`, `co-op/builders-and-backers.md`. Added:
  `co-op/launchpad-and-dex.md`. Backer and BP were removed from the glossary, and the BP
  bullet was removed from Terms §6 (see gate A).
- **Building NFTs are described only as HUNT-lockup NFTs.** *(Superseded by the Factory
  rework above: Buildings are legacy, and their page was removed.)* Main Buildings lock
  1,000 HUNT in the Town Hall. Mini Buildings put 100 HUNT into the Mint Club V2 Bond reserve
  on Base; onchain the bond shows a 0% mint royalty and a 5% burn royalty (checked
  2026-09-23).
- **HUNT supply re-synced to town-web-2's per-chain model**, which supersedes the 2026-09-08
  model below. *(The locked lines and the ledger note are superseded by the Factory rework
  above.)* Burned now includes the Ethereum and Base dead-address balances. Locked Ethereum
  is Main Buildings × 1,000 plus the Neverlose.money vault. Locked Base is the Mint Club V2
  Bond HUNT balance, which includes Mini Building HUNT. Circulation is computed per chain.
  The buyback ledger's USD figure is the current value of the total, not the value at
  execution.
- **lpTOKEN.fun runs on four chains:** Robinhood Chain, Base, Arc (native USDC) and Ethereum.
  The web app's ZapRouter addresses now match the deployment records, so the old gate B hold
  is resolved: all 24 addresses in `reference/contracts.md` were checked against
  `contracts/deployments/*.json`. Also added: the ETHOnline 2026 award and the Uniswap
  governance protocol-fee note.
- **h402 is live in beta at h402.hunt.town**, the CLI's default backend. Every
  `h402-test.hunt.town` link is gone. Updated: wallet setup (OWS signing, funding link,
  `defaultWallet`, platform limits), free calls without a wallet, settlement through the
  Coinbase CDP facilitator, the Tempo MPP upstream rail, the ARD registry endpoints, and the
  error and response envelopes.
- **Build Log** regenerated from town-web-2 `src/content/build-log.ts`: 25 entries.

### 2026-09-08: studio reframing + HUNT re-sync

*(The studio framing is superseded by the 2026-09-23 Factory rework above.)*

- **Introduction now leads with "Hunt Town is an onchain product studio."** The Builder &
  Agent Economy is woven in as *who we build for* rather than the defining label, matching
  the site's own hero ("A product studio for the onchain era" / "We build what's next.
  Onchain."). The legacy "web3 co-building community" definition was **dropped**: it
  contradicted the studio framing.
- **The two Hunt Town pages were made to cohere and reordered:**
  `The Studio Model` (how we work) now comes first, then
  `The Builder & Agent Economy` (who we build for). Each page opens by naming the other, and
  the economy page adds a table mapping each active product to the half it serves.
- **HUNT supply model changed upstream and the docs were corrected** *(superseded by the
  2026-09-23 per-chain model above)*. town-web-2 replaced
  the old "Mint Club project reserves" input with the **Neverlose.money vault**. Current
  model, now documented in `hunt/supply.md`:
  - **Burned** = 500,000,000 − canonical Ethereum total supply
  - **Locked** = Main Buildings × 1,000 + Mini Buildings × 100 + Neverlose.money vault balance
  - **Market circulation** = current Ethereum supply − locked (workbook methodology, *not*
    an exchange-reported float)
  - Base HUNT excluded, backed 1:1.
- **Buyback & Burn is no longer hypothetical.** The site's ledger is now **real verified
  history**, not the sample fixtures it held previously: 16 recorded changes totalling
  **301,087,312 HUNT** (~60% of original issuance), with Etherscan records. `hunt/buyback-and-burn.md`
  now documents that history *and* keeps the forward-looking discretionary programme clearly
  separate from it. *(The forward-looking programme is superseded: burns ended with the
  Factory rework.)*
- **Base HUNT bridge documented**: canonical `L2StandardBridge` via Superbridge (pre-filled
  HUNT route), with the third-party-infrastructure disclaimer carried from Terms.

### 2026-09-08, earlier: town-web-2 product sync

- Four active products, ordered **h402 → lpTOKEN.fun → Co-op → Mint Club**.
- **lpTOKEN.fun** added (5 pages), live on **Base and Robinhood Chain** *(now four chains, see
  2026-09-23)*.
  ⚠️ `lptoken-fun/README.md` and `docs/architecture.md` are **stale** (still say
  Robinhood-only, predating Base support) and were not used as sources.
- **h402 rewritten**: vocabulary is capability / provider / call; the **automatic router is
  retired** (`/routes/auto/*` → `410 Gone`); there is **no "verification score"**:
  verification is binary (`enabled` only after a real paid probe), and *quality score* is a
  separate ranking signal.
  ⚠️ The payments layer is pre-1.0 and churned recently (an Arc Testnet migration was merged
  and reverted the same day). Re-verify the rail before publishing. *(Re-verified
  2026-09-23: Base USDC over x402 for callers, x402 or Tempo MPP upstream.)*

## Structural decisions already applied

- **Terms stays at `/terms`.** GitBook derives URLs from the **SUMMARY group hierarchy**, not
  the file path, so Terms is listed as a **top-level** entry after a divider. Verified in a
  PR preview.
- **lpTOKEN group slug pinned to `/lptoken`.** The heading `## lpTOKEN.fun` published under
  `/lptoken.fun/...` (a literal dot in the path); the anchor form
  `## lpTOKEN.fun <a href="#lptoken" id="lptoken"></a>` fixes it.
- **Page slugs come from file names.** Inside a group, a page publishes at
  `/<group-slug>/<file name without .md>` (the PR #1 preview shows `/hunt-town/studio-model`
  and `/mint-club/mint-burn`, not their titles). Renaming a file changes its URL; changing
  an H1 does not.
- **Redirects live in `.gitbook.yaml`.** Keys are old URL paths without a leading slash;
  values are file paths relative to `root`. GitBook applies them only when the old path no
  longer resolves.
- **Site-dependent URLs to keep:** `/hunt/buyback-and-burn#the-historical-record` (the
  Factory supply panel's burn-record link), `/co-op/overview` ("About Co-op"), and `/terms`.
- **Audit links preserved** from the removed `to-do-list.md`: CertiK report / Skynet / KYC and
  the community audit in `mint-club/security-audits.md`; Hunt Town's BEOSIN audit in
  `factory-nft/migrating-buildings.md` and `reference/links.md → Security & Audits`.
