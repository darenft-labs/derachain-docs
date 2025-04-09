# Get List Collection By Owner

## Request

In order to get collections of a wallet on-chain, SDK provides you with a `getCollectionsByOwner` endpoint to do so

```typescript
try {
  const testnetClient = nft2Client.getNFT2ContractMultichain('testnet');
 
  const { collections, total } = await testnetClient.getCollectionsByOwner(
    "0x...",  // user wallet
    {
      limit: 20,
      offset: 0
    },
    [97, 43113]
  );
 
  console.log(collections, total)
} catch (e) {
  console.error(e);
}
```

## Parameters

* `ownerAddress` (string): Wallet address of owner.
* Pagination:
  * `limit` (number): Pagination limit.
  * `offset` (number): Pagination offset.
  * `sort` (`{field: 'deployAt'; order: 'DESC' | 'ASC'}`): Optional. Only support sort on collection deploy block. Default order DESC.
* `chainIds`: Which chains to get from.

## Response

{% tabs %}
{% tab title="Success" %}
```json
{
  collections: Array<{
    name: string;
    symbol: string;
    imageUrl: string;
    contractAddress: string;
    ownerAddress: string;
    creatorAddress: string;
    chainId: number;
    type: number;
    deployedAt: Date;
    totalNfts: number;
    totalOwners: number;
    kind: number;
    defaultRoyalty: number;
  }>;
  total: number;
}
```
{% endtab %}

{% tab title="Error" %}
1. Chain not supported:

```
Error: Cannot read property 'getCollectionsByOwner' of undefined
```
{% endtab %}
{% endtabs %}

