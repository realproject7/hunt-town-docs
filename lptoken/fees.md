# Fees & Economics

There is **no performance fee and no management fee** on the vault position. Swap fees
earned by the vault's own liquidity stay with holders in full.

## Where fees go

| Fee | Where it goes |
| --- | --- |
| **Vault position swap fees** | **All to holder NAV.** No skim |
| **Mint and redeem** | A small fee to the protocol treasury |
| **Launch position fees** | Shared between the creator, vault NAV and the protocol treasury |

The current rates are in the [methodology](https://lptoken.fun/methodology).

## How launch fees are distributed

Anyone can trigger the distribution of launch position fees. The NAV part goes straight into
the vault. Creator and treasury payouts are separate claims, so a recipient that cannot
accept a transfer never blocks anyone else's. The creator can hand their claim to another
address.

## Price behavior

A full-range LP position holds both sides of the pair, so measured in the pair's other
asset, an lpTOKEN share moves less than the token itself, plus the swap fees it earns. This
is not a promised volatility cap or return. See [Risks](risks.md).
