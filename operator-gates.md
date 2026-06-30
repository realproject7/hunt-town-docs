# Operator Gates

> **Not published.** This file is intentionally left out of `SUMMARY.md`, so GitBook
> ignores it on import. It is the single working checklist of everything in the docs that
> needs an operator decision, a verified figure, or a confirmed link **before publication**.
>
> Each item maps to an inline `> **TODO (operator):**` callout in the page listed. Once you
> fill a figure in the page, delete that page's callout and check the box here. Find them all
> any time with: `grep -rn "TODO (operator)" .`

20 open gates across 20 pages, plus the legal/structural notes at the bottom.

---

## 1. Token & supply figures (hard numbers)

- [ ] **HUNT supply** — `hunt/hunt-erc20.md`
  Add HUNT max/total supply, current circulating supply, and a one-line note on initial
  distribution, so the whitepaper states hard numbers rather than describing the mechanism only.
- [ ] **Building NFT counts & locked HUNT** — `hunt/building-nfts.md`
  Total issued Main and Mini Buildings (and any cap), plus cumulative HUNT locked in Building pools.
- [ ] **MINT (MT) token** — `mint-club/mint-token.md`
  MT contract address(es) and network(s), supply, buyback mechanics' parameters; confirm which
  current reward programs use MT before publishing figures.

## 2. Co-op economic constants (verify against live contracts)

- [ ] **Daily BP issuance & conversion** — `co-op/daily-backing-and-minting-flow.md`
  Confirm exact daily BP issued per Mini Building and how BP converts into mint amounts; add a
  worked numeric example.
- [ ] **BP rules** — `co-op/daily-backing-point.md`
  Precise BP-per-Mini-Building per day, any caps or decay, and exactly how BP converts to a mint
  amount, verified against the live contract. (Same constant as the item above — keep them consistent.)
- [ ] **Launch flow** — `co-op/launch-a-project-token.md`
  Concrete launch steps (name, supply, curve, reserve parameters a builder sets), any launch
  requirements/fees, and a link to the live launch interface on coop.hunt.town.

## 3. h402 — launch domain & live examples

- [ ] **Production domain (blocks several pages)** — `h402/overview.md`
  Confirm the launch domain (currently `h402-test.hunt.town`, docs at `h402-test.hunt.town/docs`;
  intended `h402.hunt.town`) and update links throughout the h402 section and `reference/links.md`.
- [ ] **Catalog browser + API** — `h402/discover-routes.md`
  Link the live catalog browser and catalog API endpoint once the domain is confirmed.
- [ ] **CLI / curl examples** — `h402/call-and-pay.md`
  Add copy-pasteable CLI and `curl` examples against a real route (e.g. `ai/image-generate`)
  once the domain and a stable demo route are fixed.
- [ ] **Agent quickstart** — `h402/for-ai-agents.md`
  Exact install command, an end-to-end example agent (e.g. Claude) calling a paid route, and
  funding instructions once finalized.
- [ ] **Provider onboarding** — `h402/for-builders.md`
  Document how a builder submits a route, sets pricing, configures the upstream, and gets listed,
  with the real Builders section link once published.
- [ ] **@h402/core SDK usage** — `h402/h402-core-sdk.md`
  Package install command, minimal `viem` and `ethers` snippets, and a link to the package README
  once the API surface is frozen for launch.

## 4. Mint Club — protocol specifics (verify against live app)

- [ ] **Supported chains for create** — `mint-club/create.md`
  Exact networks/chains Mint Club create supports today, plus any creation requirements or fees.
- [ ] **Creator-tool parameter ranges** — `mint-club/creator-tools.md`
  Confirm lock-up durations, airdrop size limits, and free-mint conditions against the live app.
- [ ] **Fees & royalty split** — `mint-club/economics.md`
  Current platform fee rate, allowed creator-royalty range, and the precise split, verified
  against the live Mint Club V2 contracts.
- [ ] **SDK package** — `mint-club/sdk.md`
  SDK package name, install command, a minimal create + mint example, and the developer-docs link.
- [ ] **Audited V2 addresses** — `mint-club/security-audits.md`
  List the audited V2 contract addresses per chain (in `reference/contracts.md`) and confirm the
  CertiK report link resolves to the current published report.
  *(Audit links themselves are now in place — CertiK report, Skynet/KYC, community audit.)*

## 5. Reference — contracts & links

- [ ] **Contract addresses** — `reference/contracts.md`
  Add Mint Club V2 core/bond addresses per chain, the MINT (MT) token address(es), and the h402
  treasury / operating wallet addresses *if* they are to be published. Confirm and precisely label
  the "Building NFT (Mainnet) contract" entry (bonding/zap contract vs. collection).
- [ ] **Social links & domains** — `reference/links.md`
  Add official social links (X, Farcaster, Discord, Telegram), confirm the h402 production domain,
  and update Co-op links once coop.hunt.town is live.
- [ ] **Canonical Base bridge** — `hunt/base-hunt.md`
  State which canonical bridge is used for HUNT between Ethereum and Base, and link the bridge UI,
  so holders have a single supported path documented.

---

## Decisions already applied (for the record)

- **Terms preserved at `/terms`.** The Terms page lives at repo root (`terms.md`), not under
  `reference/`, because GitBook URLs follow the file path — a `reference/terms.md` would have
  published at `/reference/terms` and broken the existing `https://docs.hunt.town/terms` link.
  Content was merged from the live Terms (BourbonShake Inc., 14 sections) with the studio identity
  update and a new **h402 Payments** section (now 15 sections), date bumped to 2026-06-30.
  - **Recommended:** have legal give the updated Terms a final sign-off before publish — in
    particular the new §1 Overview (studio framing) and §9 h402 Payments wording.
- **Audit links preserved.** CertiK report/Skynet/KYC + community audit are in
  `mint-club/security-audits.md`; the Hunt Town BEOSIN audit (Town Hall & Building, 2022) is in
  `hunt/building-nfts.md` and consolidated under `reference/links.md → Security & Audits`.
  These previously lived only in the now-removed `to-do-list.md`.
- **Building NFT → h402 credits** is documented as *proposed / under review* (`hunt/building-nfts.md`),
  not a live feature.
