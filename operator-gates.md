# Operator Gates

> **Not published.** This file is intentionally left out of `SUMMARY.md`, so GitBook
> ignores it on import. It is the single working checklist of everything in the docs that
> needs an operator decision, a verified figure, or a confirmed link **before publication**.
>
> Each item maps to an inline `> **TODO (operator):**` callout in the page listed. Once you
> fill a figure in the page, delete that page's callout and check the box here. Find them all
> any time with: `grep -rn "TODO (operator)" .`

20 open gates across 43 pages, plus the notes at the bottom.

---

## 1. h402 — launch domain blocks several pages

- [ ] **Production domain** — `h402/overview.md`
  h402 is **pre-launch**. The only origin configured in source is `h402.hunt.town`, which
  **does not resolve** (verified). The accessible environment is `h402-test.hunt.town`.
  Confirm the launch domain, then update every h402 link plus `reference/links.md`.
- [ ] **Catalog browser + API base URL** — `h402/discover-capabilities.md`
- [ ] **Real call examples** — `h402/call-and-pay.md`
  Replace the illustrative command with copy-pasteable CLI and `curl` examples against a
  real capability + provider.
- [ ] **Builders page + submission form** — `h402/for-builders.md`
  Add the live links, and update the page when self-serve onboarding ships (today listing is
  team-reviewed).
- [ ] **Package docs** — `h402/packages.md`
  README links and a minimal `@h402/core` snippet once the API surface is frozen.

## 2. Token & supply figures

- [ ] **Building NFT counts & locked HUNT** — `hunt/building-nfts.md`
  Total issued Main and Mini Buildings (and any cap), plus cumulative HUNT locked.
- [ ] **Buyback ledger** — `hunt/buyback-and-burn.md`
  Once the first events execute, decide whether the whitepaper restates the ledger or keeps
  pointing at the live record on hunt.town/hunt. **No figures are published until then** —
  the site's current ledger is explicitly sample/design data.
- [ ] **MINT (MT) token** — `mint-club/mint-token.md`
  Contract address(es), network(s), supply, buyback mechanics; confirm which reward programs
  use MT.

## 3. Co-op economic constants (verify against live contracts)

- [ ] **Daily BP issuance & conversion** — `co-op/daily-backing-and-minting-flow.md`
- [ ] **BP rules** — `co-op/daily-backing-point.md`
  Precise BP-per-Mini-Building per day, caps/decay, and how BP converts to a mint amount.
  (Same constant as above — keep them consistent.)
- [ ] **Launch flow** — `co-op/launch-a-project-token.md`
  Concrete launch steps, requirements/fees, and the live coop.hunt.town link.

## 4. Mint Club — verify against the live app

- [ ] **Supported chains for create** — `mint-club/create.md`
- [ ] **Creator-tool parameter ranges** — `mint-club/creator-tools.md`
- [ ] **Fees & royalty split** — `mint-club/economics.md`
- [ ] **SDK package** — `mint-club/sdk.md`
- [ ] **Audited V2 addresses** — `mint-club/security-audits.md`
  *(Audit links themselves are in place — CertiK report, Skynet/KYC, community audit.)*

## 5. Reference

- [ ] **lpTOKEN ZapRouter address** — `reference/contracts.md`
  Deliberately omitted. The contracts repo's deployment records list a **newer** ZapRouter
  than the web app's `deployment.ts` and bundled ABI, which still point at the superseded
  one. Confirm onchain which is live before publishing an address.
- [ ] **Remaining contract addresses** — `reference/contracts.md`
  Mint Club V2 core/bond per chain, MINT (MT), and the h402 treasury / operating wallet
  addresses *if* they are to be published. Confirm and label the "Building NFT (Mainnet)
  contract" entry precisely.
- [ ] **Social links** — `reference/links.md`
  X, Farcaster, Discord, Telegram; confirm the h402 domain; update Co-op links when
  coop.hunt.town is live.
- [ ] **Canonical Base bridge** — `hunt/base-hunt.md`
  Which bridge is canonical for HUNT between Ethereum and Base, plus the bridge UI link.

---

## Sync notes — 2026-09-08 update against town-web-2

The docs were re-synced to the renewed studio site (`town-web-2`) and the current product
repos. What changed, and what to be aware of:

- **Product order and count.** Now four active products, ordered
  **h402 → lpTOKEN.fun → Co-op → Mint Club**. h402 is labelled **Coming soon**, not Live.
- **lpTOKEN.fun added** as a new section (5 pages), sourced from `lptoken-fun` and
  `lptoken-contracts`. Live on **Base and Robinhood Chain**.
  ⚠️ Two files in `lptoken-fun` are **stale** and were not used: `README.md` and
  `docs/architecture.md` still describe the product as Robinhood-only (both predate the
  Base support commit). The deployed contracts on both chains are the authority.
- **h402 rewritten** for the repositioning. The old docs described a *payment protocol with
  a route catalog and an automatic router*; all three are now wrong:
  - vocabulary is **capability / provider / call** (route is internal-only),
  - the **automatic router is retired** — `/routes/auto/*` returns `410 Gone`; provider
    selection is explicit and client-pinned, with `defaultProvider` only a recommendation,
  - there is **no "verification score"** — verification is binary (`enabled` only after a
    real paid probe with the response stored as a sample); the separate *quality score* is
    a ranking signal, not a trust rating.
  - Pages `discover-routes.md`, `for-ai-agents.md`, `h402-core-sdk.md` were replaced by
    `discover-capabilities.md`, `mount.md` + `providers.md`, and `packages.md`.
  - ⚠️ The payments layer is **pre-1.0 and recently churned** (an Arc Testnet migration was
    merged and reverted the same day). Re-verify the rail before the whitepaper ships.
- **HUNT restructured** to match the site's own framing: utility in two axes (foundation for
  launched token economies; product revenue → buyback & burn), plus new
  `hunt/supply.md` and `hunt/buyback-and-burn.md`. Buybacks are documented as
  **discretionary, unscheduled, and not a guaranteed allocation**.

## Decisions already applied (for the record)

- **Terms preserved at `/terms`.** GitBook derives URLs from the **SUMMARY group hierarchy**,
  not the file path — so Terms is listed as a **top-level** entry (after a divider), not
  inside the Reference group, which is what keeps `https://docs.hunt.town/terms` working.
  Verified against a GitBook PR preview.
  - **Recommended:** legal sign-off on the updated Terms before publish — especially §1
    (studio framing) and §9 (h402 Payments). Consider whether lpTOKEN.fun warrants its own
    clause, since it is a live product with LP/fee mechanics.
- **Audit links preserved.** CertiK report/Skynet/KYC + community audit in
  `mint-club/security-audits.md`; Hunt Town's BEOSIN audit in `hunt/building-nfts.md` and
  consolidated in `reference/links.md → Security & Audits`. These previously lived only in
  the now-removed `to-do-list.md`.
- **Building NFT → h402 credits** stays documented as *proposed / under review*.
