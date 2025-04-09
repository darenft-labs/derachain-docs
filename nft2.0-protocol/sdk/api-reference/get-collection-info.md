# Get Collection Info

## Request

In order to get collection info, SDK provides you with a `getCollectionInfo` endpoint to do so

```typescript
try {
  const mainnetClient = nft2Client.getNFT2ContractMultichain('mainnet');
 
  const collection = await mainnetClient.getCollectionInfo(
    43114,
    "0x..."  // collection address
  );
 
  console.log(collection)
} catch (e) {
  console.error(e);
}
```

## Parameters

* `chainId`: Which chain to get from.
* `collectionAddress` (string): Collection contract address.
* `isFullInfo` (boolean): more infos like image, totalNfts, totalOwners. Optional

## Response

{% tabs %}
{% tab title="Success" %}
```json
{
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
}
```
{% endtab %}

{% tab title="Error" %}
1. Chain not supported:

```
Error: Cannot read property 'getCollectionInfo' of undefined
```
{% endtab %}
{% endtabs %}
