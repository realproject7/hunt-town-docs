# Trading & the HUNT Reserve

Co-op tokens trade against their own bonding curves, not an order book or a liquidity pool.
Every trade moves HUNT into or out of the token's reserve.

## Buying and selling

- **Buying** mints new tokens at the current curve price. The HUNT for the tokens goes into
  that token's reserve, and the price moves up the curve.
- **Selling** burns tokens back to the curve. HUNT comes out of the reserve at the current
  price, and the price moves down.
- **Paying with ETH or USDC.** A buyer on the Co-op can also pay in ETH or USDC. It is swapped
  to HUNT through Uniswap v4 first, so every buy still reaches the reserve as HUNT.
- **Where trades happen.** Buying and selling both happen on the Co-op. Because every Co-op
  token is a Mint Club token, it can also be traded on [mint.club](https://mint.club), against
  the same curve.

## Royalties on each side

The mint royalty is paid on top of the reserve deposit. The burn royalty comes out of what a
seller receives. Both are paid in HUNT and split 80/20 between the creator and the protocol.
Each project page shows its rates.

## Many reserves, one asset

Each token keeps its own reserve, held for it by the Mint Club V2 contract on Base, and each
reserve backs only its own token. What the projects share is the asset: every reserve is
HUNT. Each buy on any project locks more of the same asset, and HUNT held in these reserves
counts as locked in [Supply & Distribution](../hunt/supply.md). It returns to circulation
when holders sell.

## Prices in HUNT and in dollars

A token's curve price is set in HUNT. Its dollar price follows the HUNT price, so it moves
when HUNT moves, even without trades in the token itself.

<figure><img src="../.gitbook/assets/coop/coop-project.jpg" alt="Co-op project info and stats"><figcaption><p>Project stats show the price in dollars and in HUNT, and the HUNT locked in the reserve. Example project, figures at capture time.</p></figcaption></figure>
