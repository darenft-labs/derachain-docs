# Utility Functions

## Merkle Tree

1. In order to generate an merkle tree with input Whitelist, SDK provides  `buildWhitelistMerkleTree` endpoint to do so.

```typescript
import { utils } from "@darenft-labs/nft2-client";
 
const data = utils.buildWhitelistMerkleTree([
  {
    address: "0x...",       // user wallet in whitelist
    tokenIdOrAmount: 5,     // FCFS: maximum NFT amount of user, FixedUri: NFT token ID
    tokenUri: 'ipfs://XXX', // tokenUri, only for FixedUri
  },
  ...
]);
 
console.log('data: ', data);
```

2. Generate an leaf of merkle tree with input Whitelist, SDK provides an endpoint `createWhitelistLeaf` to do so

```typescript
import { utils } from "@darenft-labs/nft2-client";
 
const data = utils.createWhitelistLeaf(
  "0x...",      // user wallet address
  5,            // tokenIdOrAmount
  'ipfs://XXX', // tokenUri, only for FixedUri
);
 
console.log('data: ', data);
```

## IPFS URL converter

1. Convert url `ipfs://` to ipfs public endpoint, SDK provides `convertIPFSToUri` endpoint to do so.

```typescript
import { utils } from "@darenft-labs/nft2-client";
 
const accessableUrl = utils.convertIPFSToUri("ipfs://XXX"); // XXX is CID on IPFS
 
console.log('url: ', accessableUrl);
```

2. Convert url of an ipfs endpoint to `ipfs://` format, SDK provides `convertUrlToIPFS` endpoint to do so.

```typescript
import { utils } from "@darenft-labs/nft2-client";
 
const ipfsUrl = utils.convertUrlToIPFS("http://abc/ipfs/XXX"); // XXX is CID on IPFS
 
console.log('url: ', ipfsUrl);
```

## Multi chain

Get network type (`mainnet | testnet`) of chain id, SDK provides `getNetworkKey` endpoint to do so

```typescript
import { utils } from "@darenft-labs/nft2-client";
 
const netWorkType = utils.getNetworkKey(43113);
 
console.log('url: ', netWorkType);
```

