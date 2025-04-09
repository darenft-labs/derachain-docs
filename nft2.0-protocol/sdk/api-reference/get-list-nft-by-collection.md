# Get List NFT By Collection

## Request

In order to get list NFT of a collection, SDK provides you with a `getNFTsByCollection` endpoint to do so

```typescript
try {
  const mainnetClient = nft2Client.getNFT2ContractMultichain('mainnet');
 
  const { nfts, total } = await mainnetClient.getNFTsByCollection(
    56,
    "0x...",  // collection address
    {
      limit: 20,
      offset: 0
    }
  );
 
  console.log(nfts, total)
} catch (e) {
  console.error(e);
}
```

## Parameters

* `chainId`: Which chain to get from
* `collectionAddress` (string): Collection contract address.
* Pagination:
  * `limit` (number): Pagination limit.
  * `offset` (number): Pagination offset.
  * `sort` (`{field: 'tokenId' | 'mintedAt'; order: 'DESC' | 'ASC'}`): Optional. Default order ASC by tokenId.

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
    royalties: number;
    collection: Collection;
  }>;
  total: number;
}
```
{% endtab %}

{% tab title="Error" %}
1. Chain not supported:

```
Error: Cannot read property 'getNFTsByCollection' of undefined
```
{% endtab %}
{% endtabs %}
