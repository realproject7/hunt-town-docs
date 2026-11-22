# Contracts & Addresses

Canonical contract addresses for the Hunt Town economy. Always verify against the official
links in [Links & Resources](links.md) before transacting.

## HUNT (ERC-20)

| Network | Address |
| --- | --- |
| Ethereum | `0x9AAb071B4129B083B01cB5A0Cb513Ce7ecA26fa5` |
| Base (bridged) | `0x37f0c2915CeCC7e977183B8543Fc0864d03E064C` |

## Factory NFT

| Contract | Network | Address |
| --- | --- | --- |
| Factory NFT (ERC-1155, token id `0`, holds the vault's HUNT) | Ethereum | `0x961eA6C51c185958b1A11ad8335046988D1B5734` |

## Mint Club V2

| Contract | Network | Address |
| --- | --- | --- |
| Mint Club V2 Bond (holds every Base HUNT reserve) | Base | `0xc5a076cad94176c2996B32d8466Be1cE757FAa27` |
| MT (Mint Token, ERC-20) | Base | `0xFf45161474C39cB00699070Dd49582e417b57a7E` |

## Neverlose.money

| Contract | Network | Address |
| --- | --- | --- |
| Neverlose.money vault (its HUNT counts as locked) | Ethereum | `0x7edBE5aF30Ba6Ba2DE9EdDc72C2f585D1B0D5775` |

## Product contracts

Contracts that the apps call for payments, swaps and migrations are shown in each app, and
can change between releases. lpTOKEN.fun lists its contracts on every supported chain at
[lptoken.fun/contracts](https://lptoken.fun/contracts).

## Legacy: Building NFTs

Building NFTs are legacy assets. Holders can migrate them into Factory NFTs. See
[Migrating Buildings](../factory-nft/migrating-buildings.md).

| Contract | Network | Standard | Address |
| --- | --- | --- | --- |
| Main Building NFT | Ethereum | ERC-721 | `0x0c9Bb1ffF512a5B4F01aCA6ad964Ec6D7fC60c96` |
| Mini Building NFT | Base | ERC-1155 (id `0`) | `0x475f8E3eE5457f7B4AAca7E989D35418657AdF2a` |
| Town Hall (holds the HUNT behind Main Buildings) | Ethereum | Not a token | `0xb09A1410cF4C49F92482F5cd2CbF19b638907193` |
