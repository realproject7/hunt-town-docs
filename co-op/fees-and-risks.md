# Fees & Risks

## Fees

| Fee | Amount | Where it goes |
| --- | --- | --- |
| **Creation fee** | Mint Club's creation fee (0.0007 ETH on Base), plus gas | Mint Club |
| **Mint royalty** | Set by the builder, 0% to 50% (1% by default) | 80% creator, 20% Mint Club protocol |
| **Burn royalty** | Set by the builder, 0% to 50% (1% by default) | 80% creator, 20% Mint Club protocol |
| **Project update** | Currently 10 HUNT per update | Burned |

Royalties are paid in HUNT. See [Economics](../mint-club/economics.md) for how Mint Club
royalties work.

## Risks

- **Independent projects.** Co-op tokens are created by their builders. They are not
  operated, controlled or endorsed by the Hunt Town team, and appearing on the Co-op is not a
  recommendation. See [Terms](../terms.md).
- **A steep curve.** Every token launched on the Co-op uses the same preset curve, and its price climbs steeply as
  supply grows. Early and late buyers pay very different prices.
- **Royalties on both sides.** A buy and a sell each pay a royalty, so a quick round trip
  returns less HUNT than it cost, unless both royalties are 0%.
- **Dollar value follows HUNT.** Prices are set in HUNT, so a token's dollar value moves with
  the HUNT price.
- **Reserve depth.** Only the HUNT paid into a token backs it, so a token with few buyers has
  a thin reserve.
- **Contracts.** Co-op tokens run on Mint Club V2 contracts, and buys paid in ETH or USDC
  also pass through a Uniswap v4 swap. Mint Club's audits cover the Mint Club V2 contracts,
  not the Co-op's swap contract. See [Security & Audits](../mint-club/security-audits.md).
