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
- [ ] **Ship the whitepaper describing a pre-launch product?**
  h402 is marked *Coming soon* in the Introduction, and `h402/overview.md` has a Status
  section saying the production domain is not live and links point to
  `h402-test.hunt.town`. Confirm this is how you want the whitepaper to read at publication,
  or hold the h402 section until launch.
- [ ] **Terms — legal sign-off.** Especially §1 (studio framing) and §9 (h402 Payments).
  Also decide whether **lpTOKEN.fun deserves its own clause**: it is a live product with LP,
  fee, and permanent-lock mechanics, and Terms currently has no section specific to it.
- [ ] **Co-op domain.** `reference/links.md` lists Co-op as `coop.hunt.town` *(moving)*.
  Confirm the destination and timing, then drop the "(moving)" qualifier.

## B. Deliberately omitted — do not publish until verified

- [ ] **lpTOKEN ZapRouter address** — omitted from `reference/contracts.md` on purpose.
  The contracts repo's deployment records list a **newer** ZapRouter than the web app's
  `deployment.ts` and bundled ABI, which still point at the superseded one. The two disagree;
  confirm onchain which is live before publishing any address.
- [ ] **h402 treasury / operating wallet addresses** — decide whether these should be public
  at all. Currently not listed.

## C. Detail to add when available

Each of these has a page that reads fine today; the gate is extra specificity.

| What | Page |
| --- | --- |
| Building NFT issued counts, any cap, cumulative HUNT locked | `hunt/building-nfts.md` |
| Daily BP per Mini Building, caps/decay, BP→mint conversion (verify against live contracts) | `co-op/daily-backing-point.md`, `co-op/daily-backing-and-minting-flow.md` |
| Concrete launch steps, requirements/fees, live launch link | `co-op/launch-a-project-token.md` |
| Mint Club: supported chains, creator-tool parameter ranges, platform fee + royalty split, SDK package name | `mint-club/create.md`, `creator-tools.md`, `economics.md`, `sdk.md` |
| MINT (MT) address, networks, supply, buyback parameters | `mint-club/mint-token.md` |
| Mint Club V2 audited contract addresses per chain | `mint-club/security-audits.md`, `reference/contracts.md` |
| h402: live catalog browser + API base URL, real CLI/`curl` examples, Builders page + form URL, package READMEs | `h402/discover-capabilities.md`, `call-and-pay.md`, `for-builders.md`, `packages.md` |
| Official social links (X, Farcaster, Discord, Telegram) | `reference/links.md` |
| Canonical "Building NFT (Mainnet) contract" role — label it precisely | `reference/contracts.md` |

---

## Sync notes

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
- **HUNT supply model changed upstream and the docs were corrected.** town-web-2 replaced
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
- **lpTOKEN.fun** added (5 pages), live on **Base and Robinhood Chain**.
  ⚠️ `lptoken-fun/README.md` and `docs/architecture.md` are **stale** (still say
  Robinhood-only, predating Base support) and were not used as sources.
- **h402 rewritten**: vocabulary is capability / provider / call; the **automatic router is
  retired** (`/routes/auto/*` → `410 Gone`); there is **no "verification score"** —
  verification is binary (`enabled` only after a real paid probe), and *quality score* is a
  separate ranking signal.
  ⚠️ The payments layer is pre-1.0 and churned recently (an Arc Testnet migration was merged
  and reverted the same day). Re-verify the rail before publishing.

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
