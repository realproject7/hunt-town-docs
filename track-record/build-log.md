# The Build Log

Everything Hunt Town has shipped since 2018: the products, experiments, and partner builds that
got the studio to where it is. **25 projects**, newest first.

Each entry records four things: **the bet** we made (or, for partner builds, **the collab**),
**what worked**, **what broke**, and the field that matters most for a studio, **what it
seeded** in the products we run today.

Legend: **Still live** = operating today · **Sunset** = retired · **Sunset → {name}** = retired
and succeeded by a named product · 🤝 = partner/collab build. Index numbers are chronological, so
#001 is the oldest.

---

## #025 · Clap · 2025 · Sunset → Co-op

A Farcaster mini-app that gamifies builder-content discovery — "Swipe Right. Clap to Earn."

- **The bet:** Make discovering and rewarding good builder content as effortless as swiping —
  turn curation into a daily, dopamine-friendly loop on top of the Hunt Tip reward engine. Spend
  a daily Clap Points allowance by swiping right / clapping on great posts; the more you clap,
  the more $HUNT you earn via the Hunt Tip reward system. Mint Mini Building NFTs (+100 points
  each) to expand your allowance; deploy Super Clap to quote-cast standout content; a daily
  leaderboard pays the top 3 Mini Building NFTs from the Builder Grant pool.
- **What worked:** Strong launch traction — within one week, Mini Building NFT minting rose 65%
  and 852,700 HUNT was locked up through the added ecosystem activity.
- **What broke:** Sunset alongside the broader tipping program when Hunt Town pivoted from
  recognizing posts to backing actual projects — replaced by the Co-op.
- **What it seeded:** Validated swipe-to-curate as a builder-discovery mechanic and deepened the
  HUNT/Building-NFT loop — feeding into the Co-op's engagement model.
- **Meta:** 2025-06 · Base / Farcaster (mini-app) · [Clap launch
  post](https://news.hunt.town/p/introducing-clap-swipe-right-clap)

---

## #024 · MintDrop · 2025 · Sunset

A daily spin-to-earn Farcaster mini-app — hold $MT, spin daily, win $MT-backed token rewards.

- **The bet:** A low-friction daily raffle as a new-user acquisition funnel for Mint Club —
  players had to trade their won / airdropped tokens on Mint Club, pulling Base + Farcaster
  users into the ecosystem ("the more $MT you hold, the higher your win range").
- **What worked:** By day 68 (~2 months): 176,772 spins = 176,772 onchain Base transactions,
  $18,222 of $MT paid out to spinners (~$0.1031/spin), and 79 $MT child tokens created
  organically. Most importantly it pushed the Mint Club app to #1 overall on Farcaster and the
  Base app — sustained for a long stretch (the user-acquisition goal, achieved).
- **What broke:** Built as an acquisition engine for Mint Club rather than an end in itself —
  once it had driven that growth (and the #1 ranking), it was wound down.
- **What it seeded:** Proved the daily-engagement reward loop and the Farcaster Mini App channel
  as a powerful top-of-funnel for Mint Club.
- **Meta:** 2025-04 · Base / Farcaster Mini App · [launch
  post](https://x.com/MintClubPro/status/1910261260052296134) · [day-68
  traction](https://x.com/MintClubPro/status/1937781101659136371)

---

## #023 · Hyped.club · 2025 · Sunset

A token-trading app where "hTokens" are backed by an original token but engineered to amplify
its price volatility — trade hot tokens with extra beta.

- **The bet:** Traders want higher-beta exposure — wrap an existing token in a bonding-curve
  "hToken" that amplifies its moves, giving a leveraged feel without lending or perps.
- **What worked:** Demonstrated extreme amplified moves (e.g. an hToken running +4,985% / 24h
  against its base) and reached real visibility — ranked in the Base app's top 12. Markets
  paired each token with its hyped twin (DICKBUTT ↔ hDICKBUTT, BNKR ↔ hBNKR, etc.).
- **What broke:** Two reasons: (1) in a market where meme-coin volatility was already extreme,
  there wasn't enough demand to seek out even more volatile trades; and (2) because it used a
  bonding-curve price model rather than custody, there were inherent limits to how accurately it
  could amplify the underlying's volatility.
- **What it seeded:** Pushed Mint Club bonding curves into "derivative-like,"
  structured/amplified exposure — beyond plain token/NFT creation.
- **Meta:** 2025-03 · Base / Mint Club · [launch
  post](https://x.com/hypedtokens/status/1904429282723811548)

---

## #022 · PumpSea · 2024 · Sunset

A platform built on Mint Club to trade NFTs like meme coins — buy and sell NFTs on bonding
curves, Pump.fun-style.

- **The bet:** Combine the instant-liquidity, speculative UX of Pump.fun with the NFT focus of
  OpenSea — bonding curves make NFTs tradable instantly, no DEX liquidity pools needed.
- **What worked:** Triggered explosive early trading — many NFTs hit 20–30 ETH each in volume in
  the early days. Its Pump.fun-style creator royalties were seen as a fresh, novel mechanic by
  the market. (Precise aggregate traction is hard to recover.)
- **What broke:** The NFT market deteriorated, draining demand for speculative NFT trading; the
  product was sunset.
- **What it seeded:** Proved Mint Club's bonding-curve engine could power NFT trading + a
  consumer trading UI — the "trade-like-coins," chart, and portfolio pattern echoed in later
  experiments (Hyped.club, MintDrop).
- **Meta:** 2024-12 · Base / Mint Club · [launch
  post](https://x.com/MintClubPro/status/1867095408494997644)

---

## #021 · Hamcaster · 2024 · Sunset · 🤝

A SocialFi app to tokenize your Farcaster profile ("Caster Tokens") and share daily $HAM
rewards.

- **The collab:** Built and led by founder deployer (now the founder of BankrCoin) on the Mint
  Club protocol — Hunt Town / Mint Club's role was protocol support; deployer built the SocialFi
  / staking / locking / voting layer and the Ham + Farcaster integration.
- **What worked:** Shipped a full third-party SocialFi token economy with in-app DeFi primitives
  (stake for rewards, lock for votes, tip in-feed) on its own chain. (Exact traction numbers are
  unrecoverable — see below.)
- **What broke:** Two things ended it: Ham Chain (the L2 it ran on) shut down operations, and
  founder deployer refocused on his next project, BankrCoin, winding Hamcaster down. Because the
  chain itself is gone, precise traction figures can't be retrieved.
- **What it seeded:** Proved Mint Club's contracts could power a full third-party SocialFi token
  economy on a different chain entirely — not just on our own surface.
- **Meta:** 2024-08-30 · Ham Chain (L2) + Farcaster · Founder: deployer (now BankrCoin) ·
  [hamcaster.com](https://hamcaster.com/) · [mechanics
  intro](https://paragraph.com/@deployer/the-mechanics-of-hamcaster) · [launch:
  Farcaster](https://farcaster.xyz/deployer/0x00f3759a) ·
  [tn100x](https://x.com/tn100x/status/1829179240484626858) · [wind-down
  note](https://farcaster.xyz/deployer/0xda19c69a)

---

## #020 · MCDegen · 2024 · Sunset · 🤝

Use your Farcaster $DEGEN tip allowance to mint tokens — instead of tipping content, spend tips
to mint Mint Club bonding-curve tokens issued on Degen Chain (L3).

- **The collab:** A collab where Hunt Town / Mint Club led development and operations, with
  support from the Degen team (whose DEGEN Tip allowance was the spend rail). The minted tokens
  are Mint Club bonding-curve tokens on Degen Chain.
- **What worked:** Became a runaway hit — at its peak, over one-third of all daily $DEGEN tips
  were being spent on minting Mint Club Degen-L3 tokens (see traction chart).
- **What broke:** The Degen team shut it down. DEGEN-tip usage had skewed so heavily toward
  MCDegen that they judged it no longer fit DEGEN Tip's intended purpose (rewarding content).
- **What it seeded:** Showed Mint Club tokens could plug into an existing external
  social-tipping rail ($DEGEN) as a mint/spend destination on another chain — so effectively it
  dominated that rail.
- **Meta:** 2024-08-21 · Degen Chain (L3) / Farcaster · Mint Club–led, Degen-team-supported ·
  [launch post](https://news.hunt.town/p/buy-tokens-with-your-degen-tips) · [shutdown
  note](https://farcaster.xyz/jacek/0x8706342d)

---

## #019 · Hunt Tip · 2024 · Sunset → Co-op

A Farcaster tipping / rewards system where Building-NFT holders give daily tip allowances to
recognize and reward Web3 builders, via seasonal leaderboards and grants.

- **The bet:** Reward builders inside the social feed — turn Building NFT ownership into a daily
  tipping allowance and recurring community influence, paired with seasonal Builder/Tipper
  Grants.
- **What worked:** Anchored a long-running seasonal builder-rewards program — across 17 seasons
  / ~17 months it generated 306,182,411+ tips & claps and supported 921 builders through grants,
  establishing Hunt Town's Base + Farcaster builder community. It became the reward engine that
  Clap was later built on.
- **What broke:** As the ecosystem grew, the appreciation model (tipping posts) hit its limits —
  Hunt Town pivoted from recognizing posts to backing actual projects, replacing the program
  with the Co-op (the current hunt.town).
- **What it seeded:** The NFT-allowance → tipping/grants model and the Base + Farcaster builder
  community — the foundation Clap was built on and the direct predecessor of the Co-op.
- **Generations:**
  - **V1 (~Jul 2024):** monthly ranking — top-3 builders won 100 / 60 / 40 Mini Building NFTs
    per month. Building NFTs grant daily tip allowances (Main = 1,000 / Mini = 100).
  - **V2 (Feb 3, 2025):** shifted monthly → daily ranking so far more builders could earn (daily
    3 / 2 / 1 Mini Building NFTs for 1st–3rd), with wallet-connected personal ranking on the
    Hunt Tip site; Tipper Grants unchanged.
- **Meta:** 2024-07 · Base / Farcaster · [V1
  launch](https://x.com/steemhunt/status/1818826061251330257) · [V2
  launch](https://news.hunt.town/p/introducing-hunt-tip-v2) · [Goodbye Clap, Hello
  Co-op](https://news.hunt.town/p/goodbye-clap-hello-co-op)

---

## #018 · MCTraveller · 2024 · Sunset · 🤝

McDonald's With Traveller: an art raffle where the entry ticket was itself a bonding-curve NFT
on Base, and the prizes were original art and travel.

- **The collab:** A collaboration between the $MEMBER community and Seoul-based artist Yongoh
  Kim, run on Mint Club. The site put it plainly: a chance to win original art and exclusive
  merchandise through a ticket purchase and raffle entry, merging digital currency with
  traditional art for a members-only audience. Mint Club supplied the mechanism, an ERC-1155
  ticket on a bonding curve on Base priced in $MEMBER, and by the team's account the prize pool
  as well.
- **What worked:** The buying and entry flow was simple. You bought a ticket on the bonding
  curve, then sent the ticket NFT to the artist's address to enter, and more tickets meant
  better odds. Anyone who did not want to enter could sell the ticket back into the curve
  instead. The terms only allowed the raffle to run once the 1000-ticket curve was full, and the
  sale ran close to that cap before submission closed on 16 April 2024. The draw was set for 18
  April 2024, to be run live on stream and announced in the /members-only channel on Farcaster.
  Every entrant received the artwork NFT collection as a gift, win or lose, and the Season 1
  prize pool ran from an original 45.5x45.5cm painting and goods to twenty A2 limited prints, a
  round-trip plane ticket, a tour voucher, McDonald's vouchers and a hotel voucher.
- **What broke:** The team's read is that the $MEMBER community faded fast, and the
  collaboration ended with it. The product framed itself as Season 1, down to a ticket NFT named
  "MC Traveller Raffle S1", but there is no sign a second season ever ran. The domain is gone
  too: mctraveller.xyz is now parked and listed for sale.
- **What it seeded:** It used a Mint Club bonding curve as a raffle ticket rather than as a
  collectible: same primitive, different job, with the curve pricing the ticket, gating when the
  draw could run, and giving anyone who changed their mind a way back out. It also sits in the
  2024 Base and Farcaster run this archive records, alongside Farcards, Hunt Tip and Hamcaster.
- **Meta:** 2024-04-08 · Base · Yongoh Kim · [launch
  post](https://x.com/gami_vc/status/1777235281303028184) · [raffle ticket NFT
  (MCTS1)](https://mint.club/nft/base/MCTS1) · [/members-only
  channel](https://farcaster.xyz/~/channel/members-only) · [Yongoh Kim on
  Foundation](https://foundation.app/@YONGOHKIM)

---

## #017 · Farcards · 2024 · Still live · 🤝

Collectible NFT trading cards on Farcaster — your profile becomes a tradable card.

- **The collab:** Built and run by an independent Farcaster builder team; Hunt Town / Mint
  Club's role was protocol support only (the cards are ERC-1155 NFTs on the Mint Club
  bonding-curve protocol, with max 1,000 supply per collection). Card value tracks Farcaster
  account stats.
- **What worked:** 18,000+ Farcards created. It reached real Base/Farcaster prominence — Base
  co-founder Jesse Pollak minted his own Farcard — and the project has a public Dune dashboard.
  Physical Farcards even showed up at BaseCamp.
- **What broke:** Farcaster community activity dropped sharply and the broader NFT market
  deteriorated — together draining the social-collectible demand the product depended on.
- **What it seeded:** Demonstrated Mint Club's curves as a drop-in primitive for viral,
  social-stat-driven collectibles inside Farcaster.
- **Meta:** 2024-04 · Base / Farcaster · Independent Farcaster builder team ·
  [far.cards](https://far.cards) · [Dune dashboard](https://dune.com/sqx/farcards) · [news
  article](https://news.cnyes.com/news/id/5620153)

---

## #016 · Memberify · 2024 · Sunset · 🤝

Mint your own bonding-curve membership NFT — fans/community join by minting your personal
"member" card.

- **The collab:** Built and led by the Member team (gami); Hunt Town / Mint Club's role was
  protocol support only — each membership is an ERC-1155 NFT on the Mint Club bonding-curve
  protocol (Base), backed by the $member token.
- **What worked:** 1,383 membership collections were created, and the ecosystem locked 24M+
  $member. It reached real Base prominence — Base co-founder Jesse Pollak minted his own member
  NFT.
- **What broke:** It went viral on Farcaster for a while but couldn't sustain the traction;
  eventually founder Gami refocused on other projects, and the collaboration wound down.
- **What it seeded:** Another proof that external teams can build social-token products on Mint
  Club — here the "personal membership token" pattern — reinforcing Mint Club as a platform
  partners build on.
- **Meta:** 2024-02 · Base / Farcaster · Member team (gami) · [launch
  post](https://x.com/gami_vc/status/1755414573858062796)

---

## #015 · Town Poker · 2023 · Sunset

A Texas hold'em bot that dealt a full tournament inside the Hunt Town Discord, played for
virtual points with no real money at stake.

- **The bet:** The point was to put the whole game where the community already was. The studio's
  account is that members played with Build Points, the town's virtual points; on screen the bot
  deals and counts everything in chips. No real money was in it and there was nothing to cash
  out.
- **What worked:** The whole game ran in chat. Players acted by tapping buttons on the bot's
  message instead of typing commands, and the bot posted the felt as a rendered image branded
  hunt.town. It handled the parts that usually break a chat game: a turn timer that auto-folded
  idle players and kicked them after three idle turns, hands dealt back to back with a ten
  second gap, and side pots when players went all in. It ran as a knockout tournament with
  everyone starting at 1,000 chips, and one hand in the captures seats ten players with the
  community chat running in the same channel.
- **What broke:** It was never gambling for money. The studio's account is that there could
  still have been legal or regulatory issues, and that was not a risk worth carrying for a
  community game. By that account it ran for a single event, the evening of 19 May 2023 that
  these captures come from, and then it stopped.
- **What it seeded:** This one seeded nothing, and it is honest to say so: it was a single
  community event, not the start of a product line. What it showed is that a real-time
  multiplayer game could run end to end inside the chat surface the community was already in, on
  virtual points with nothing cashable in it.
- **Meta:** 2023-05-19

---

## #014 · Chatcasso · 2022 · Sunset

An AI NFT wizard that lived in a chat window. You described the art you wanted, it drew it,
deployed the collection on-chain, and gave it a public mint page.

- **The bet:** In 2022 we saw three separate jobs in making an NFT collection: get the art,
  deploy a contract, build a mint page. We thought one chat could do all three. Describe a style
  or upload a reference, approve what the bot draws, fill in a short form, and the collection
  goes live on BNB Chain with a mint page anyone can open.
- **What worked:** It won first place in the Lifestyle in Web3 track at a BNB Chain hackathon
  held in Seoul on Dec 17-19, 2022, and took a $5,000 BUSD prize. It ran as a working demo, not
  a mock. The bot generated artwork from a text prompt or an uploaded image, let you accept it
  or hit retry, then deployed a real collection to BNB Chain, Goerli or Mumbai from inside the
  same chat. Every collection got a public page where a stranger could mint the next edition,
  with a numbered editions grid and a link out to OpenSea.
- **What broke:** It never formally launched. By our own account we were getting the launch
  ready. Binance announced its own AI NFT tool, Bicasso, on March 1, 2023, two months after the
  hackathon. [Cointelegraph reported on March
  5](https://cointelegraph.com/news/bnb-chain-hackathon-winner-accuses-binance-of-stealing-ai-powered-nfts-idea)
  that Binance had been accused of copying the hackathon winner, and that Binance said an
  internal review left it confident Bicasso was developed independently. The launch was dropped.
  Chatcasso stayed a working demo and never shipped.
- **What it seeded:** Chatcasso was built on generative AI in December 2022, earlier than
  anything else in this archive. We carried none of the code forward. What carried was the habit
  of building on a new capability while it is still new.
- **Meta:** 2022-12-20 · BNB Chain · [launch announcement
  (X)](https://x.com/heyproject7/status/1604988057819951104) · [Cointelegraph
  coverage](https://cointelegraph.com/news/bnb-chain-hackathon-winner-accuses-binance-of-stealing-ai-powered-nfts-idea)
  · [KED Global coverage](https://www.kedglobal.com/korean-startups/newsView/ked202303030008)

---

## #013 · Dixel Club V2 · 2022 · Still live

A pixel-NFT collection factory. A creator launches a 24x24 canvas as their own collection, and
anyone can mint a color-variant edition of it on a bonding curve.

- **The bet:** V1 proved people would draw together, but the artists wanted collections of their
  own, not one canvas everybody shared. So Dixel was rebuilt as a factory: a creator sets the
  artwork, supply, mint price, royalty and start time, and their followers mint color variants
  of it. Same on-chain, refundable-reserve model, handed to the creator instead of the crowd.
- **What worked:** The team raised seed funding from VistaLabs and Edimus Capital, announced 6
  May 2022, and was picked as one of the top 5 projects in the Klaytn Incubation Program,
  announced 7 April 2022. V2 shipped to mainnet on 27 June 2022, straight after a community
  security audit that ran on a $10,000 USDT bounty. It is still running, now across Base,
  Ethereum, Polygon, BNB Chain and Kaia, and in practice people use it like POAP: on-chain proof
  of attendance and commemorative collectibles.
- **What broke:** The NFT market cooled sharply after the 2021 peak and took the draw-to-earn
  demand with it. V2 kept the minting tool alive but never got to be the social platform the
  first generation was chasing.
- **What it seeded:** DIXEL was minted on the Mint Club protocol from the start. The fully
  on-chain (vector, base64) collectible with a refundable reserve fed straight into Mint Club's
  NFT tooling and its multi-chain direction.
- **Meta:** 2022-06-27 · Multi-chain: Base / Ethereum / Polygon / BNB Chain / Kaia ·
  [dixel.club](https://dixel.club) · [V2 investment + launch
  plan](https://news.hunt.town/p/dixel-club-receives-investment-dixel) · [Klaytn Incubation
  Program](https://news.hunt.town/p/dixel-club-joins-klaytn-incubation)

---

## #012 · Dixel Club V1 · 2022 · Sunset → Dixel Club V2

One shared 16x16 pixel canvas on BNB Chain. Anyone could overwrite pixels and mint the result as
an SVG-based NFT, earning $DIXEL when someone later painted over their work.

- **The bet:** We drew a line against script-generated collections. We believed one people drew
  by hand, together on a shared canvas, was worth more. We called it the first-ever Draw to Earn
  digital collectible platform, and the rules matched: 100% community-made pixel art, and all
  profits to the community, not to the team.
- **What worked:** Mainnet went live on BNB Chain on 7 February 2022, at block height 15040000,
  with a launch airdrop to the AirNFT, PancakeSwap NFT, BakerySwapV3 NFT, MintedVodka and Mint
  Club communities. It shipped as a full product, not a demo: a drawing editor, a gallery, a
  rewards page, a burn-for-refund flow, a marketplace and a $DIXEL buy flow. The economics were
  on-chain: each pixel cost 0.1% more after every overwrite, 10% of a mint split among everyone
  who had painted those pixels before, and the other 90% held in a refundable reserve the owner
  could claim by burning the NFT. One undated capture of the live gallery shows the shared
  canvas at edition #877 with 170,485 overwritten pixels.
- **What broke:** The idea was novel, but demand for making pixel art turned out thinner than we
  expected. The people who did show up were artists, and they did not want to share a single
  canvas with everyone else. They wanted their own collection, with their own followers minting
  color variants of it.
- **What it seeded:** That demand became Dixel Club V2, which is still live. DIXEL itself was
  minted on the Mint Club protocol, so V1 ran on the curves the studio still builds on.
- **Meta:** 2022-02-07 · BNB Chain (BSC) · [V1 launch
  post](https://news.hunt.town/p/meet-the-draw-to-earn-pixelfi-nft) · [V1 launch post (Steemit
  original)](https://steemit.com/dixel/@steemhunt/meet-the-draw-to-earn-pixelfi-nft-platform-dixel-club-mainnet-launch)

---

## #011 · 1s.market · 2021 · Sunset · 🤝

A marketplace to tokenize and trade anyone's time as "time tokens." Tagline: "'Second' is the
ultimate currency — determine the value of a person's time by trading in a time asset market."

- **The collab:** The first-ever third-party project built on Mint Club. Partner tx0x (a Korean
  blockchain dev firm — 10+ yrs, prior builder of the 9cscan explorer) built and independently
  operated the marketplace; Mint Club provided contract-level technical support. Time tokens
  were backed by the MINT collateral contract (one token per person). tx0x owned the project and
  ultimately shut it down.
- **What worked:** Reached ~1.3M "seconds" of time assets generated on-platform (per the app's
  own counter). Its founding idea traces to InTime, which won 1st place at the Upbit hackathon
  in Oct 2019 — a validated, award-winning concept before it became a Mint Club build.
- **What broke:** Timing. Tokenizing and trading someone's time is an accepted idea today, but
  in 2021 it was too radical for the market — the concept arrived early. (It was also
  partner-owned, so the partner's decision to end it closed the book.)
- **What it seeded:** The proof-of-concept that external teams could build standalone products
  on Mint Club — validating Mint Club as a platform/protocol, not just a first-party app. The
  conceptual ancestor of later partner builds (Farcards, Hamcaster).
- **Meta:** 2021-12 · BNB Chain · tx0x · [official launch
  post](https://news.hunt.town/p/the-official-launch-of-1smarket-the) · [partnership
  announcement](https://steemit.com/mintclub/@steemhunt/strategic-partnership-with-tx0x-to-develop-a-time-based-marketplace-on-mint-club)
  · [InTime — Upbit hackathon 1st place (Oct 2019)](https://youtu.be/FZMxNNxPcPA?t=67)

---

## #010 · Mint Club V1 · 2021 · Sunset → Mint Club V2

A no-code token builder on BNB Chain. Anyone could launch a BEP20 token in a few clicks, and a
bonding curve backed by MINT made it tradable right away with no liquidity pool.

- **The bet:** We believed complexity was the biggest barrier to mass adoption. So Mint Club
  took out the two hardest parts of launching a token, writing the contract and bootstrapping
  liquidity. The launch post went out under the title "The first-ever no-code/no-LP-required
  token building platform on the Binance Smart Chain".
- **What worked:** Binance Labs took Mint Club into its Incubation Program season 3, announced
  on 11 Nov 2021. It was a 10-week program, and Mint Club was one of 9 startups selected from
  396 teams. Outside teams started shipping on the protocol: Musing.io and Debate Monkey were
  already live by then, with 1s.market, DecisionDaddy and TMI Club scheduled to join. One
  explorer capture shows $20,153,834.10 in total value locked and 1,026 smart tokens, which is
  what the explorer showed when it was captured, not an audited lifetime figure.
- **What broke:** Every smart token on V1 shared one collateral root, the MINT token. The team's
  read was that the market had moved past that: builders wanted several root tokens across
  several chains, and capital was flowing to Ethereum L2s like Base. The collateral root was a
  design decision rather than something to patch, so we rebuilt the protocol as Mint Club V2.
- **What it seeded:** Mint Club V2, the protocol the studio runs today. Later products in this
  archive run on the Mint Club protocol rather than on V1: PumpSea, Hyped.club and MintDrop,
  plus partner builds like Farcards, Hamcaster and Memberify. V1 also closed a loop back to
  HUNT, because trading fees from trades without a referral code went to the quarterly HUNT
  burn.
- **Meta:** 2021-07-13 · BNB Chain (BEP20) · [official launch
  post](https://steemit.com/mintclub/@steemhunt/official-launch-the-first-ever-no-code-no-lp-required-token-building-platform-on-the-binance-smart-chain)
  · [Binance Incubation
  Program](https://steemit.com/mint/@steemhunt/mint-club-joins-binance-incubation-program)

---

## #009 · Neverlose.money · 2020 · Still live

A gamified HODL / savings protocol that pays bonuses to disciplined long-term lockers, funded by
early-exit penalties from those who break their lock.

- **The bet:** Behavioral finance on-chain — force long-term holding by penalizing early
  withdrawal and redistributing those penalties to the holders who stayed. "Earn bonus from
  losers."
- **What worked:** Shipped working Ethereum HODL lock-up contracts (ETH / BTC / HUNT). At its
  peak it reached ~$24.15M cumulative lock-ups and ~$489.5K total bonus generated for
  disciplined holders.
- **What broke:** After the peak, the meme-coin trend on Ethereum L1 sent gas fees to abnormal,
  sustained highs — a single lock-up transaction could cost $400–500 in gas. That made the
  deposit/lock loop economically unviable for most users, and the protocol lost momentum.
- **What it seeded:** Pioneered our on-chain lock-up + penalty-redistribution mechanics, which
  carried into Mint Club's lock-up tooling.
- **Meta:** 2020-12 · Ethereum · [neverlose.money](https://neverlose.money) · [launch
  post](https://steemit.com/neverlosemoney/@steemhunt/hunt-s-4th-dapp-neverlose-money-is-officially-launched-today)

---

## #008 · Nomadtask · 2020 · Still live

A bounty-based marketing-task marketplace pairing product makers with "digital nomads" who
complete paid micro-tasks (reviews, social actions, content).

- **The bet:** Reinvent grassroots marketing — let makers crowdsource cheap, authentic promotion
  and pay a global pool of digital nomads in crypto / USD-pegged rewards.
- **What worked:** After the February 2020 relaunch it passed 80,000+ sign-ups and hit strong
  active-user growth (peak ~39K MAU / ~29K WAU / ~11K DAU). It went viral on YouTube — a creator
  with ~490K subscribers featured it in a video that drew 1M+ views and 1,400+ comments, and an
  ~80K-subscriber creator's video drew 221K views and 300+ comments — driving large organic
  sign-up waves.
- **What broke:** Popularity became the problem. As the platform blew up, abusers flooded in
  (concentrated in a few countries — e.g. Bangladesh, Nigeria), and fighting abuse soaked up
  disproportionate engineering/ops resources. At the same time the "earn online / side-income"
  space turned into a red ocean, competition intensified, and profitability eroded.
- **What it seeded:** Cemented the quest / task-incentive marketplace model in our playbook —
  the through-line to Hunt Tip grants and Clap — and proved HUNT as a reward currency beyond
  Steem.
- **Meta:** 2020-07 · [nomadtask.com](https://nomadtask.com) · [Reviewhunt has a new name —
  Nomadtask](https://steemit.com/nomadtask/@steemhunt/reviewhunt-has-a-new-name-nomadtask) ·
  [YouTube #1 (490K subs, 1M+ views)](https://www.youtube.com/watch?v=qb4zBKHwdQ0) · [YouTube #2
  (80K subs, 221K views)](https://www.youtube.com/watch?v=KHKPTHlidn0)

---

## #007 · Gudoks · 2020 · Sunset

A Korean-run marketing service that paid people already active in reward communities to follow a
client's social channel, with each follow verified by screenshot before payout.

- **The bet:** The bet was that people already active in reward communities would follow a
  brand's channel for a small cash reward, and that checking each follow by hand would keep
  those followers real accounts rather than bot traffic. The pitch was that a client never hands
  over account credentials: they give the public URL of the channel they want to grow, and
  Gudoks does the rest.
- **What worked:** Gudoks never asked for a client's social account login. A client pasted the
  public URL of the channel they wanted to grow and left an email address, then signed in
  through a link sent to that email, with no password to set. The campaign form covered
  Instagram, Facebook, Twitter, TikTok and YouTube, and let the advertiser scope the audience to
  Korean users only or open it to everyone. Rewards were paid in Korean won, and only after a
  participant submitted a screenshot of the completed follow and it passed review.
- **What broke:** The team's account is that abusive users showed up and that reviewing their
  submissions became the expensive part of running it: every follow needed a person to look at a
  screenshot and decide whether it counted. By that account the cost of policing that queue
  outran what the campaigns brought in, so Gudoks was shut down. The domain no longer resolves.
- **What it seeded:** The thread here is a lesson, not shared code: pay a reward only against
  evidence that the work actually happened. Reviewhunt, three months later, took the same shape
  into its Nomadtask era and ran into an abuse problem of its own.
- **Meta:** 2020-04-21 · [Launch video (YouTube)](https://www.youtube.com/watch?v=3vitFdilo0o) ·
  [Gudoks channel (YouTube)](https://www.youtube.com/channel/UCG2KXAT-aDiR4pprXiKwF9g)

---

## #006 · CoronaTasks · 2020 · Sunset

A one-page directory of sites that paid for small remote tasks, built during the 2020 lockdowns.

- **The bet:** The pitch was in the tagline: a hand-picked list of websites where you can earn
  easy money while quarantined. Every card carried the same three stats: daily visitors, payout
  method, and rewards per task. A badge on each card said how hard the work was.
- **What worked:** It launched on Product Hunt on April 6, 2020 and finished #7 Product of the
  Day. The whole product was one page: a category filter row, a card per site, and a group chat
  panel called Quarantiners Chat where people posted under anonymous color-and-animal handles. A
  47-second launch video went up on the Hunt Town channel the same day.
- **What broke:** coronatasks.com is gone. The domain now resolves to a for-sale parking page.
  The team's own account is that it was planned as a short run from the start, and that the
  COVID moment it was built for faded fast.
- **What it seeded:** The first site on the list was Reviewhunt, our own product, renamed
  Nomadtask later that year, which has its own entry in this archive. Past that it was a
  one-off. What it left behind was the shape of a small directory: one page, one filter row, and
  the same stats on every card, so listings could be compared side by side.
- **Meta:** 2020-04-06 · [Product Hunt launch (#7 Product of the
  Day)](https://www.producthunt.com/posts/coronatasks) · [launch video
  (47s)](https://www.youtube.com/watch?v=gjidzyWLJTc)

---

## #005 · Testfly · 2020 · Sunset

A marketplace for on-demand beta tests. Makers wrote a test instruction, and verified testers
around the world ran it and sent back screenshots and written feedback.

- **The bet:** We already had the testers. Steemhunt, Reviewhunt and LOL Hunt had gathered an
  audience, and the site promoted the top 25% of members from those communities into a verified
  tester pool. Testfly was the attempt to sell that pool to app makers: on-demand testers and
  feedback for a dollar. The pitch claimed 65,000 or more verified testers in 150 or more
  countries.
- **What worked:** The loop worked end to end. A maker filled in three fields, app name, store
  link and a test instruction, and the job went out to the tester pool. Testers ran it and
  returned proof, either a screenshot or a video capture, with written feedback attached. Our
  own demo campaign ran against Bark, a map-based social app, and over two days in March 2020
  the dashboard filled with dated testers from the Philippines, Bangladesh, South Korea, Vietnam
  and elsewhere. The feedback that came back read as real paragraphs, not boilerplate.
- **What broke:** The team's read is that demand failed, not supply. Testers were never the
  constraint, but makers with a real beta-test need were. Nothing public survives about how many
  campaigns ran, and testfly.app no longer resolves.
- **What it seeded:** Testfly is a clear case of one of our products feeding the next: its
  supply side was cut straight out of Steemhunt, Reviewhunt and LOL Hunt, so a crowd we already
  ran became the raw material for a new product. Building a product on a crowd we already had,
  instead of buying one, is the pattern this entry records.
- **Meta:** 2020-04-02 · [Product Hunt
  launch](https://www.producthunt.com/products/testfly/launches/testfly)

---

## #004 · LOL Hunt · 2019 · Still live

A daily top chart of the funniest YouTube clips, shared and upvoted by users worldwide.

- **The bet:** The Steemhunt "community-curated daily leaderboard" formula could extend beyond
  products to entertainment — with user data kept private via decentralized storage.
- **What worked:** Won 2nd Prize in the Blockstack "Can't Be Evil" contest and reached #5
  Product of the Day on Product Hunt — validating the decentralized-storage curation pattern.
- **What broke:** The decline of the Blockstack ecosystem — in particular its pivot to Stacks (a
  Bitcoin L2) — hollowed out the app ecosystem LOL Hunt was built on, leaving the original
  Blockstack-era apps without a living platform underneath them.
- **What it seeded:** Extended our "curated daily upvote leaderboard" UX beyond products into
  entertainment, and gave the team hands-on decentralized-identity/storage experience
  (Blockstack Auth + Gaia).
- **Meta:** 2019-12 · Blockstack (Auth + Gaia storage; React front-end, Rails/Postgres back-end)
  · [lol.hunt.town](https://lol.hunt.town/) · [Product Hunt
  launch](https://www.producthunt.com/products/reviewhunt-beta/launches/lol-hunt) ·
  [Devpost](https://devpost.com/software/lol-hunt)

---

## #003 · DRG OTC · 2019 · Sunset

A public board for peer-to-peer token trades. You pasted a Bitberry escrow link, the site read
it and listed it, and anyone could join the trade without signing up.

- **The bet:** Bitberry had just shipped a free escrow service for person-to-person token
  trades, and HUNT had been listed on the wallet about a month earlier. Hunters wanted somewhere
  to share those trade links. Bitberry's own share modal said it plainly: it did not offer a
  marketplace for traders. We built the marketplace layer and left the escrow to them.
- **What worked:** The core of the product was one input row: a source dropdown, a field for the
  escrow URL, and an Add Trade button. Paste a Bitberry link and the site read the expiry, the
  price and the token details off it, then listed the trade for anyone to join in one click. Two
  features arrived after the launch announcement and were the better half of the product: a
  Margin column that priced each trade against the market so you could see the spread before
  taking it, and a Telegram bot that posted every new trade to a group. Most tokens on the board
  were marked Unlisted, with no exchange price at all, which is what OTC is actually for.
- **What broke:** It held no funds and ran no matching engine. Every row on the board started as
  a Bitberry escrow link, so the product rested on one company staying in business, and it
  inherited that company's rules, and the launch post warned you might hit a KYC requirement
  before you could use the escrow at all. The team's read is that Bitberry shut down its
  business, and when the escrow went, the board had nothing left to list.
- **What it seeded:** Nothing later grew directly out of it, but it taught the studio something
  about position: we had built the thin layer on someone else's rails, and the company
  underneath could end our product by closing its own. Mint Club later put us on the other side
  of that line, as the rails other teams build on.
- **Meta:** 2019-09-27 · Ethereum · [Introducing DRG
  OTC](https://steemit.com/steemhunt/@steemhunt/introducing-drg-otc-otc-token-trading-site)

---

## #002 · Reviewhunt · 2019 · Sunset → Nomadtask

A review-campaign marketplace where makers paid early adopters in HUNT to run quests on a new
app, leave a store review, then post about it on their own channel.

- **The bet:** The bet was that makers would rather pay for a finished funnel than for raw
  installs. So a campaign was a ladder: try the product, clear two required quests, take an
  optional bonus quest for a bigger payout, leave a store review, then post about it. Rewards
  were paid in HUNT, and a buying bot at Daybit Exchange bought HUNT whenever a maker funded a
  campaign, so maker spend fed the token.
- **What worked:** Round 1 went live on July 31, 2019 with a $10,500 campaign budget and real
  makers on it: BUZZi, Mosaeek, and tata by TTC Protocol. The landing page published one
  finished campaign in full. HAIRFIT ran Aug 30 to Sep 16, 2019, spent $1,000, and came back
  with 197 app downloads, 30 App Store reviews, 133 Play Store reviews and 153 pieces of buzz
  content. Payouts were denominated in HUNT with a live dollar figure next to every number, and
  buzz was priced rather than guessed: the platform read a connected account's follower count
  and engagement rate, then quoted a per post estimate to the maker.
- **What broke:** It did not fail, it got rebuilt. Reviewhunt 2.0 relaunched on Product Hunt on
  Feb 12, 2020 under a new line, "Turn your marketing mission into a game-like quest", and in
  July 2020 the team renamed the product Nomadtask, saying Reviewhunt could "expand its target
  scope into a broader area" as an on-demand task marketplace for digital nomads.
  review.hunt.town started redirecting to nomadtask.com, so the 2019 product has no address of
  its own left.
- **What it seeded:** Reviewhunt is the first half of Nomadtask: the same product, renamed in
  July 2020, so its build log continues in that entry. What it worked out here was the quest
  ladder itself: small guided tasks paying HUNT rewards, with a moderator checking every proof
  before it counted.
- **Meta:** 2019-07-31 · [Reviewhunt is LIVE ($10,500 Round 1
  budget)](https://steemit.com/reviewhunt/@steemhunt/reviewhunt-live-try-cool-products-get-rewards-usd10-500-campaign-budget-for-round-1)
  · [Product Hunt (Reviewhunt
  Beta)](https://www.producthunt.com/products/reviewhunt-beta/launches/reviewhunt-1) ·
  [Reviewhunt has a new name:
  Nomadtask](https://steemit.com/nomadtask/@steemhunt/reviewhunt-has-a-new-name-nomadtask)

---

## #001 · Steemhunt · 2018 · Still live

A Product-Hunt-style daily leaderboard where curators earn crypto for sharing and upvoting cool
products. Where it all started.

- **The bet:** A passionate community of tech early adopters could out-curate centralized
  directories if rewarded directly — an ad-free, self-sustaining curation economy on the
  blockchain.
- **What worked:** Steemhunt gained major global attention well beyond the Steem community — it
  became the world's 7th-biggest DApp (per State of the DApps). At its peak it reached ~414K MAU
  / ~279K WAU / ~37K DAU and gathered 1.7M+ Steem Power delegated (worth $6M+ at the time). It
  also doubled as a single sign-on gateway — "one account to use all Steem dApps" (400+
  Steem-based apps).
- **What broke:** Two ecosystem shocks stripped the product of sustainability: (1) the Smart
  Media Token (SMT) standard the Steem Foundation had planned — and which Steemhunt's roadmap
  depended on — was indefinitely postponed/cancelled; and (2) the Steem blockchain hard-forked,
  splitting the community into Steem and Hive, fracturing Steemhunt's user base and the chain it
  was built on.
- **What it seeded:** The origin of Hunt Town's entire thesis — token-incentivized communities
  and reward-driven curation — that runs through everything we build today.
- **Meta:** 2018-03 · Steem · [steemhunt.com](https://steemhunt.com) · [Introducing
  Steemhunt](https://steemit.com/steemdev/@steemhunt/introducing-steemhunt-daily-ranking-of-effortlessly-cool-products-fueled-by-steem-blockchain)
  · [HUNT airdrops for
  Steemians](https://steemit.com/steemit/@steemhunt/announcing-hunt-token-airdrops-for-steemians-smart-media-token-project)
  · [Sponsor report
  #21](https://steemit.com/steemhunt/@steemhunt/hunt-token-airdrop-will-be-revised-or-sponsor-report-21)
