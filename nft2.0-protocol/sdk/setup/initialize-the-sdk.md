# Initialize the SDK

## Installation

```bash
npm add @darenft-labs/nft2-client
```

## Configuration

```typescript
import { NFT2Client } from "@darenft-labs/nft2-client";
 
const apiKey = 'xxx'; // API Key from NFT2 console
const nft2Client = new NFT2Client(apiKey);
 
await nft2Client.initialize().then(() => {
    console.log('Client init success: ', nft2Client);
});
```

The SDK will automatic load configuration from API server (`GET: /configs/internal-config`). However, you can set your alternative configuration as you want.

```typescript
import { ChainConfig } from "@darenft-labs/nft2-client";
 
const configs: ChainConfig[] = [{
  chainId: 1,
  providerUrl: "https://eth-mainnet.nodereal.io/v1/xxx",
  factoryAddress: "0xabcd",
  subQueryEndpoint: "https://api.subquery.network/sq/xxx"
}]
nft2Client.updateConfig(configs)
```

## Parameters

_NFT2Client_:

* `apiKey` (string): Account API key.
* `apiEndpoint` (string): endpoint of protocol API. Optional. Using for multiple environment.

_ChainConfig_:

* `chainId` (number): chain id of current chain.
* `providerUrl` (string): RPC endpoint for current chain.
* `factoryAddress` (string): Factory contract address on current chain.
* `subQueryEndpoint` (string): Subquery endpoint for current chain.

NOTE: when update config manually, all `chainId`, `providerUrl`, `factoryAddress`, `subQueryEndpoint` is required. If some chains hadn't configured, you couldn't call SDK function for those chain.
