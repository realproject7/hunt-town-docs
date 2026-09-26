# Contracts & Addresses

Canonical contract addresses for the Hunt Town economy. Always verify against the official
links in [Links & Resources](links.md) before transacting.

## HUNT (ERC-20)

| Network | Address |
| --- | --- |
| Ethereum | `0x9AAb071B4129B083B01cB5A0Cb513Ce7ecA26fa5` |
| Base (bridged) | `0x37f0c2915CeCC7e977183B8543Fc0864d03E064C` |

## Mint Club V2

| Contract | Network | Address |
| --- | --- | --- |
| Mint Club V2 Bond (holds every Base HUNT reserve) | Base | `0xc5a076cad94176c2996B32d8466Be1cE757FAa27` |

The supply method reads this contract's HUNT balance and subtracts the reserve behind the
legacy Mini Buildings. See [Supply & Distribution](../hunt/supply.md).

## Payments (h402)

| Asset | Network | Address |
| --- | --- | --- |
| USDC (settlement) | Base | `0x833589fcd6edb6e08f4c7c32d4f71b54bda02913` |

## lpTOKEN.fun

Deployed on **Robinhood Chain** (chain id `4663`), **Base** (`8453`), **Arc** (`5042`), and
**Ethereum** (`1`). Addresses are taken from the protocol's own deployment records.

| Contract | Robinhood Chain | Base |
| --- | --- | --- |
| LpTokenFactory | `0xDd9b4a30FFf71A391A39FbaCed43e3DAa84dbC84` | `0x3384eD0d272dE35bF6DC516E1eA7d188CEb51793` |
| LpTokenVault (implementation) | `0xBaf91d6c83fe4B325ddD818aDaa9A39D490E6C6d` | `0x78aae2fD8f8b09994d0e936Ce4478a7EB8FE92D9` |
| TokenLaunchpad | `0xC3612550Fd0f3095B6636110e5b06dD4eb05e000` | `0xED14eE7501fB212f876714a68308564cD6772000` |
| LaunchLiquidityVault | `0x7FcA8E7a8376B38f3eb23F21e8C7b7c6E5f3f077` | `0x39f3C534E6962Fd5fb0DD3653B6c16400c49C498` |
| LpTokenZapRouter | `0x19e1AbAcB318C25D9888bBAa62cBaa69dA2F66c7` | `0xc4C8071D651F093C4A5c2C06e7BFfc163A057DdA` |
| LpTokenLens | `0x8bA19810F56E455276a0Db1eaace071D75B08Fd2` | `0x6DC57E44B995c56F91a6AD5f221F372C1c2FFBF5` |

| Contract | Arc | Ethereum |
| --- | --- | --- |
| LpTokenFactory | `0x37F540de37afE8bDf6C722d87CB019F30e5E406a` | `0x37F540de37afE8bDf6C722d87CB019F30e5E406a` |
| LpTokenVault (implementation) | `0x2c692DB9203EF651745AF2c07ebd587222D55a06` | `0x2c692DB9203EF651745AF2c07ebd587222D55a06` |
| TokenLaunchpad | `0xa790B0e77FD23504342404fc8DD0c5AE4DE4e000` | `0xC011111853f63e9A3c5b112CEF26Ff78351c2000` |
| LaunchLiquidityVault | `0x124ed8F31A4052cA910E98e5eC9bb182C88AB365` | `0xCC61892B6F3eD6F2Bf258b53DD41683E0c2998Ab` |
| LpTokenZapRouter | `0x905F3AE86108c6A3b1a345dACEaef6c4749Ec66a` | `0x905F3AE86108c6A3b1a345dACEaef6c4749Ec66a` |
| LpTokenLens | `0x5dfA75b0185efBaEF286E80B847ce84ff8a62C2d` | `0x5dfA75b0185efBaEF286E80B847ce84ff8a62C2d` |

The factory, vault implementation, zap router, and lens share one address on Arc and
Ethereum because they were deployed deterministically.

Individual LP vaults are deterministic clones of the vault implementation, one per pool;
their addresses are listed per market in the app. The live contract table is published at
[lptoken.fun/contracts](https://lptoken.fun/contracts).

## Legacy: Building NFTs

Building NFTs are legacy assets. Holders can migrate them into Factory NFTs. See
[Migrating Buildings](../factory-nft/migrating-buildings.md).

| Contract | Network | Standard | Address |
| --- | --- | --- | --- |
| Main Building NFT | Ethereum | ERC-721 | `0x0c9Bb1ffF512a5B4F01aCA6ad964Ec6D7fC60c96` |
| Mini Building NFT | Base | ERC-1155 (id `0`) | `0x475f8E3eE5457f7B4AAca7E989D35418657AdF2a` |
| Town Hall (holds the HUNT behind Main Buildings) | Ethereum | Not a token | `0xb09A1410cF4C49F92482F5cd2CbF19b638907193` |
