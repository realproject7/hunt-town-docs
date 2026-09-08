# Contracts & Addresses

Canonical contract addresses for the Hunt Town economy. Always verify against the official
links in [Links & Resources](links.md) before transacting.

## HUNT (ERC-20)

| Network | Address |
| --- | --- |
| Ethereum | `0x9AAb071B4129B083B01cB5A0Cb513Ce7ecA26fa5` |
| Base (bridged) | `0x37f0c2915CeCC7e977183B8543Fc0864d03E064C` |

## Building NFTs

| Asset | Network | Standard | Address |
| --- | --- | --- | --- |
| Main Building NFT | Ethereum | ERC-721 | `0x0c9Bb1ffF512a5B4F01aCA6ad964Ec6D7fC60c96` |
| Mini Building NFT | Base | ERC-1155 (id `0`) | `0x475f8E3eE5457f7B4AAca7E989D35418657AdF2a` |
| Building NFT (Mainnet) contract | Ethereum | — | `0xb09A1410cF4C49F92482F5cd2CbF19b638907193` |

## Payments (h402)

| Asset | Network | Address |
| --- | --- | --- |
| USDC (settlement) | Base | `0x833589fcd6edb6e08f4c7c32d4f71b54bda02913` |

## lpTOKEN.fun

Deployed on **Base** (chain id `8453`) and **Robinhood Chain** (chain id `4663`).

| Contract | Base | Robinhood Chain |
| --- | --- | --- |
| LpTokenFactory | `0x3384eD0d272dE35bF6DC516E1eA7d188CEb51793` | `0xDd9b4a30FFf71A391A39FbaCed43e3DAa84dbC84` |
| LpTokenVault (implementation) | `0x78aae2fD8f8b09994d0e936Ce4478a7EB8FE92D9` | `0xBaf91d6c83fe4B325ddD818aDaa9A39D490E6C6d` |
| TokenLaunchpad | `0xED14eE7501fB212f876714a68308564cD6772000` | `0xC3612550Fd0f3095B6636110e5b06dD4eb05e000` |
| LaunchLiquidityVault | `0x39f3C534E6962Fd5fb0DD3653B6c16400c49C498` | `0x7FcA8E7a8376B38f3eb23F21e8C7b7c6E5f3f077` |
| LpTokenLens | `0x6DC57E44B995c56F91a6AD5f221F372C1c2FFBF5` | `0x8bA19810F56E455276a0Db1eaace071D75B08Fd2` |

Individual LP vaults are deterministic clones of the vault implementation, one per pool;
their addresses are listed per market in the app. The live contract table is published at
[lptoken.fun/contracts](https://lptoken.fun/contracts).

> **TODO (operator):** the **ZapRouter** address is deliberately omitted here. The
> contracts repo's deployment records list a newer ZapRouter than the web app's config and
> bundled ABI, which still point at the superseded one. Confirm onchain which router is live
> before publishing an address.

> **TODO (operator):** add Mint Club V2 core/bond contract addresses per chain, the MINT (MT)
> token address(es), and the h402 treasury / operating wallet addresses if they are to be
> published. Confirm the role of the "Building NFT (Mainnet) contract" entry above (bonding /
> zap contract vs. collection) and label it precisely.
