# ⟠ use-muticall ⟠

A library to get user [ERC-20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) balances and tokens price on EVM blockchains using the [Multicall smart contract](https://github.com/joshstevens19/ethereum-multicall/)

## Installation

```
npm install @dapp-builder/use-muticall

```

## Example

```typescript
import { 
  getBalancesSingleToken,
  getBalanceMultipleTokens,
  getNativePrice,
  getTokensPrice,
} from "@dapp-builder/use-muticall";

const BSC_RPC_URL = "https://bsc-dataseed1.ninicoin.io";

const userAddresses = [
  "0xF977814e90dA44bFA03b6295A0616a897441aceC", // Binance wallet
  "0x8894E0a0c962CB723c1976a4421c95949bE2D4E3", // Binance wallet
];

const contractTokens = [
  "0x55d398326f99059fF775485246999027B3197955", // USDT
  "0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d", // USDC
];

let balances;

balances = await getBalanceMultipleTokens({
  userAddress: userAddresses[0],
  contractTokens,
  rpcUrl: BSC_RPC_URL,
});

console.log(balances);

balances = await getBalancesSingleToken({
  userAddresses,
  contractToken: contractTokens[0],
  rpcUrl: BSC_RPC_URL
})

console.log(balances);

const price = await getNativePrice(BSC_RPC_URL);
console.log(price.toString())

const tokensPrice = await getTokensPrice(
    [
      "0x3e098C23DCFBbE0A3f468A6bEd1cf1a59DC1770D", // YU
      "0x9E0335fb61958Fe19Bb120F3F8408B4297921820", // FFE
    ],
    BSC_RPC_URL
  );
console.log(tokensPrice.map((price) => price.toString()));

```

## Supports

The below networks are supported when getting token price
| Chain                   | Chain ID   |
| ----------------------- | ---------- |
| Mainnet                 | 1          |
| Arbitrum                | 420        |
| Avalanche               | 43114      |
| Fuji                    | 43113      |
| BNB Smart Chain         | 56         |
| Polygon                 | 137        |
| Mumbai                  | 80001      |
| Optimism                | 10         |

The below networks are supported when getting balances

| Chain                   | Chain ID   |
| ----------------------- | ---------- |
| Mainnet                 | 1          |
| Kovan                   | 3          |
| Rinkeby                 | 4          |
| Görli                   | 5          |
| Ropsten                 | 10         |
| Sepolia                 | 42         |
| Optimism                | 10         |
| Optimism Kovan          | 69         |
| Optimism Görli          | 100        |
| Arbitrum                | 420        |
| Arbitrum Görli          | 42161      |
| Arbitrum Rinkeby        | 421611     |
| Polygon                 | 137        |
| Mumbai                  | 80001      |
| Gnosis Chain (xDai)     | 11155111   |
| Avalanche               | 43114      |
| Avalanche Fuji          | 43113      |
| Fantom Testnet          | 4002       |
| Fantom Opera            | 250        |
| BNB Smart Chain         | 56         |
| BNB Smart Chain Testnet | 97         |
| Moonbeam                | 1284       |
| Moonriver               | 1285       |
| Moonbase Alpha Testnet  | 1287       |
| Harmony                 | 1666600000 |
| Cronos                  | 25         |
| Fuse                    | 122        |
| Songbird Canary Network | 19         |
| Coston Testnet          | 16         |
| Boba                    | 288        |
| Aurora                  | 1313161554 |
| Astar                   | 592        |
| OKC                     | 66         |
| Heco Chain              | 128        |
| Metis                   | 1088       |
| RSK                     | 30         |
| RSK Testnet             | 31         |
| Evmos                   | 9001       |
| Evmos Testnet           | 9000       |
| Thundercore             | 108        |
| Thundercore Testnet     | 18         |
| Oasis                   | 26863      |
| Celo                    | 42220      |
| Godwoken                | 71402      |
| Godwoken Testnet        | 71401      |
| Klatyn                  | 8217       |
| Milkomeda               | 2001       |
| KCC                     | 321        |
| Etherlite               | 111        |
