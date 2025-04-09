# Get List NFT By Owner

## Request

In order to get list NFT of a wallet, SDK provides you with a `getNFTsByOwner` endpoint to do so

```typescript
try {
  const mainnetClient = nft2Client.getNFT2ContractMultichain('mainnet');
 
  const { nfts, total } = await mainnetClient.getNFTsByOwner(
    "0x...",  // user wallet
    {
      limit: 20,
      offset: 0
    },
    [56, 43114]
  );
 
  console.log(nfts, total)
} catch (e) {
  console.error(e);
}
```

## Parameters

* `ownerAddress` (string): Wallet address of owner.
* Pagination:
  * `limit` (number): Pagination limit.
  * `offset` (number): Pagination offset.
  * `sort` (`{field: 'tokenId' | 'mintedAt'; order: 'DESC' | 'ASC'}`): Optional. Default order ASC by tokenId.
  * `filter` (`{isDerivative: false | true}`): Optional. If true, get list derivative NFT of user. Default false.
* `chainIds`: Which chains to get from.

## Response

{% tabs %}
{% tab title="Success" %}
```json
{
  nfts: Array<{
    name: string;
    description: string;
    tokenId: string;
    chainId: number;
    creatorAddress: string;
    ownerAddress: string;
    imageUrl: string;
    tokenUri: string;
    type: number;
    status: number;
    mintedAt: Date;
    openAt?: Date; // derivative only
    closeAt?: Date; // derivative only
    royalties: number;
    collection: Collection;
    original?: { // original NFT info, derivative only
      collectionAddress: string;
      tokenId: string;
    };
    dataRegistry?: {
      providerAddress: string;  // data registry address, derivative only
    };
  }>;
  total: number;
}
```
{% endtab %}

{% tab title="Error" %}
1. Chain not supported:

```
Error: Cannot read property 'getNFTsByOwner' of undefined
```
{% endtab %}
{% endtabs %}
