# Mint & Burn

Factory NFTs are minted and burned against the HUNT in the vault. There is no bonding curve
and no order book. Both use the NAV: the vault's HUNT divided by the number of NFTs.

## Mint

Minting creates new Factory NFTs at the current NAV.

```
HUNT to mint q NFTs = HUNT in the vault × q ÷ NFTs in supply, rounded up
```

That works out to 1,000 HUNT × the multiplier for each NFT. At launch, one NFT locks 1,000
HUNT.

- **All of it goes into the vault.** The HUNT you lock stays in the Factory NFT contract and
  backs every NFT.
- **Existing holders are not diluted.** New NFTs bring in their full share of HUNT, so the
  NAV per NFT does not drop. Rounding up keeps any remainder in the vault.
- **Pay with HUNT, ETH, USDC or USDT.** HUNT goes straight in. ETH, USDC and USDT go through
  the zap router. It swaps them for exactly the HUNT needed through Uniswap V4, mints in the
  same transaction, and sends back any input it did not use. On hunt.town the most you send
  allows for price moves (0.5% for the NAV and 1% for the swap), and the transaction must
  land within 20 minutes of sending.
- **You set a maximum.** HUNT can reach the vault between your quote and your transaction,
  which raises the lock-up slightly. A HUNT mint carries the most HUNT you will lock, 0.5%
  above the quote on hunt.town. An ETH, USDC or USDT mint carries the most of that token you
  will spend. If the price moves past that maximum, the mint fails and nothing is locked.

## Burn

Burning destroys Factory NFTs and sends you HUNT.

```
HUNT you receive = HUNT in the vault × q ÷ NFTs in supply × 95%, rounded down
```

- **The burn fee is 5%.** It stays in the vault and raises the NAV per NFT for everyone
  still holding.
- **You can only burn your own.** A burn takes NFTs from the caller's wallet. An approval
  to transfer your NFTs does not let anyone burn them from your wallet or redeem them for
  you, though an approved operator can still move them.
- **The last NFT stays.** Supply can never drop below one, so the last Factory NFT cannot
  be burned.
- **You set a minimum.** Every burn carries the least HUNT you will accept.

On hunt.town the burn panel works it out for you: 1,000 HUNT × the multiplier × the NFTs you
burn gives their NAV, and the 5% fee comes off that.

### One burn or several

A single burn prices every NFT in it at the same starting NAV. Separate burns can give back
slightly more HUNT in total, because each one leaves its 5% fee behind for the NFTs that
remain.

For example, with 3,000 HUNT behind 3 NFTs, burning 2 in one transaction pays 1,900 HUNT.
Burning them one at a time pays 950 HUNT and then 973.75 HUNT, 1,923.75 HUNT in total. Each
burn is its own transaction, with its own gas cost.

## A worked example

At launch the vault holds 1,000 HUNT behind the one seed NFT.

1. Someone mints one NFT and locks 1,000 HUNT. The vault now holds 2,000 HUNT behind two
   NFTs, still 1,000 HUNT each.
2. They burn it straight away and receive 950 HUNT. The 50 HUNT fee stays behind.
3. The vault now holds 1,050 HUNT behind one NFT. The NAV per NFT is 1,050 HUNT, and the
   multiplier reads ×1.0500.

The burner got back 95% of what they locked. The NFT that stayed now has more HUNT behind it.

## What you get back in HUNT

For a holder, the whole picture fits in one line:

```
HUNT back ÷ HUNT locked = 0.95 × multiplier at burn ÷ multiplier at mint
```

- Burn at the multiplier you minted at, and you get back 95% of the HUNT you locked.
- You get back more HUNT than you locked only after the multiplier has risen more than 5.26%
  since your mint.
- All of this is counted in HUNT. The dollar value follows the HUNT price, which can fall.

No deposit is scheduled, so the multiplier may not rise at all. No return is promised. See
[Terms](../terms.md).
