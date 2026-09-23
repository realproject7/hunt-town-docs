# Operator Gates

> **Not published.** This file is intentionally left out of `SUMMARY.md`, so GitBook ignores
> it on import.
>
> **The published docs now contain zero `TODO (operator)` callouts.** Every page reads as
> final copy. This file is the *only* remaining record of what is still unverified,
> undecided, or deliberately omitted — so it must be read before the docs are treated as
> final. Nothing below blocks the merge; each item is either "add detail later" or "a
> decision only the operator can make."

---

## A. Decisions only the operator can make

These are not missing facts — they are editorial or business calls.

- [ ] **Building NFT → h402 credits — publish or cut.**
  `hunt/building-nfts.md` carries a ~70-line section documenting a credits mechanic that
  was **built, then removed from the h402 launch MVP**. It is clearly labelled
  *"Status: proposed / under review"*, and `h402/mount.md` and `h402/how-paying-works.md`
  reference it. **This is the only substantial block of non-shipped functionality in the
  whitepaper.** Decide: keep it as a documented future direction, or cut it until it ships.
  Everywhere else, Building NFTs are described only as HUNT-lockup NFTs (decided 2026-09-23).
- [ ] **Co-op publish timing.** The Co-op pages, the glossary, Terms and the HUNT pages now
  describe Co-op after the daily BP, voting, airdrop-claim and donation removal (2026-09-23).
  The live app still runs those mechanics. Decide whether to publish with the new Co-op
  release or before it. Merging the docs PR publishes everything at once.
- [ ] **Terms — legal sign-off.** Especially §1 (studio framing) and §9 (h402 Payments).
  The 2026-09-23 edits also need a look: §1 now says the products connect "builders, holders,
  and AI agents" (was "backers"), "backing or minting" became "buying or minting", and §6
  dropped the Backing Points / rewards bullet and now defines Building NFTs as NFTs minted by
  locking HUNT.
  Also decide whether **lpTOKEN.fun deserves its own clause**: it is a live product with LP,
  fee, and permanent-lock mechanics, and Terms currently has no section specific to it.
- [ ] **Co-op domain.** `reference/links.md` lists Co-op as `coop.hunt.town` *(moving)*.
  Confirm the destination and timing, then drop the "(moving)" qualifier.

## B. Deliberately omitted — do not publish until verified

- [ ] **h402 treasury / operating wallet addresses** — decide whether these should be public
  at all. Currently not listed. The treasury is already visible as the payee in every `402`
  challenge and in the public ARD entries, so listing it would not reveal anything new.

## C. Detail to add when available

Each of these has a page that reads fine today; the gate is extra specificity.

| What | Page |
| --- | --- |
| Building NFT issued counts, any cap, cumulative HUNT locked | `hunt/building-nfts.md` |
| Concrete launch steps, requirements/fees, live launch link | `co-op/launch-a-project-token.md` |
| Mint Club: supported chains, creator-tool parameter ranges, platform fee + royalty split, SDK package name | `mint-club/create.md`, `creator-tools.md`, `economics.md`, `sdk.md` |
| MINT (MT) address, networks, supply, buyback parameters | `mint-club/mint-token.md` |
| Mint Club V2 audited contract addresses per chain | `mint-club/security-audits.md`, `reference/contracts.md` |
| h402: Builders submission form URL, package README links | `h402/for-builders.md`, `packages.md` |
| Official social links (X, Farcaster, Discord, Telegram) | `reference/links.md` |
| Canonical "Building NFT (Mainnet) contract" role — label it precisely | `reference/contracts.md` |

---

## Sync notes

### 2026-09-23: Co-op pivot, HUNT re-sync, lpTOKEN chains, h402 beta

- **Co-op is now a HUNT-backed launchpad and DEX.** Per the operator, the daily Backing
  Points → voting → airdrop-claim loop and HUNT donations (with the Donors leaderboard) are
  gone from the docs. Deleted: `co-op/daily-backing-point.md`,
  `co-op/daily-backing-and-minting-flow.md`, `co-op/builders-and-backers.md`. Added:
  `co-op/launchpad-and-dex.md`. Backer and BP were removed from the glossary, and the BP
  bullet was removed from Terms §6 (see gate A).
- **Building NFTs are described only as HUNT-lockup NFTs.** Main Buildings lock 1,000 HUNT
  in the Town Hall. Mini Buildings put 100 HUNT into the Mint Club V2 Bond reserve on Base;
  onchain the bond shows a 0% mint royalty and a 5% burn royalty (checked 2026-09-23).
- **HUNT supply re-synced to town-web-2's per-chain model**, which supersedes the 2026-09-08
  model below. Burned now includes the Ethereum and Base dead-address balances. Locked
  Ethereum is Main Buildings × 1,000 plus the Neverlose.money vault. Locked Base is the
  Mint Club V2 Bond HUNT balance, which includes Mini Building HUNT. Circulation is computed
  per chain. The buyback ledger's USD figure is the current value of the total, not the
  value at execution.
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

### 2026-09-08 — studio reframing + HUNT re-sync

- **Introduction now leads with "Hunt Town is an onchain product studio."** The Builder &
  Agent Economy is woven in as *who we build for* rather than the defining label, matching
  the site's own hero ("A product studio for the onchain era" / "We build what's next.
  Onchain."). The legacy "web3 co-building community" definition was **dropped** — it
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
  separate from it.
- **Base HUNT bridge documented**: canonical `L2StandardBridge` via Superbridge (pre-filled
  HUNT route), with the third-party-infrastructure disclaimer carried from Terms.

### 2026-09-08 — earlier: town-web-2 product sync

- Four active products, ordered **h402 → lpTOKEN.fun → Co-op → Mint Club**.
- **lpTOKEN.fun** added (5 pages), live on **Base and Robinhood Chain** *(now four chains, see
  2026-09-23)*.
  ⚠️ `lptoken-fun/README.md` and `docs/architecture.md` are **stale** (still say
  Robinhood-only, predating Base support) and were not used as sources.
- **h402 rewritten**: vocabulary is capability / provider / call; the **automatic router is
  retired** (`/routes/auto/*` → `410 Gone`); there is **no "verification score"** —
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
- **Audit links preserved** from the removed `to-do-list.md`: CertiK report / Skynet / KYC and
  the community audit in `mint-club/security-audits.md`; Hunt Town's BEOSIN audit in
  `hunt/building-nfts.md` and `reference/links.md → Security & Audits`.
