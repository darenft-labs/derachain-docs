# Get List Derivative NFT By Original

## Request

In order to get list NFT derived from an original NFT, SDK provides you with a `getNFTsByOriginal` endpoint to do so

```typescript
try {
  const mainnetClient = nft2Client.getNFT2ContractMultichain('mainnet');
 
  const { nfts, total } = await mainnetClient.getNFTsByOriginal(
    43114,
    "0x...",  // original collection address
    "123",  // original token id
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

* `chainId`: Which chain to get from.
* `originCollectionAddress` (string): Original collection contract address.
* `originTokenId` (string): Original NFT token ID.
* Pagination:
  * `limit` (number): Pagination limit.
  * `offset` (number): Pagination offset.
  * `sort` (`{field: 'mintedAt'; order: 'DESC' | 'ASC'}`): Optional. Default order DESC.

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
    ownerAddress: string;
    imageUrl: string;
    tokenUri: string;
    type: number;
    status: number;
    mintedAt: Date;
    openAt: Date;
    closeAt: Date;
    royalties: number;
    original: {
      collectionAddress: string;
      tokenId: string;
    };
    dataRegistry: DataRegistry;
  }>;
  total: number;
}
```
{% endtab %}

{% tab title="Error" %}
1. Chain not supported:

```
Error: Cannot read property 'getNFTsByOriginal' of undefined
```
{% endtab %}
{% endtabs %}
