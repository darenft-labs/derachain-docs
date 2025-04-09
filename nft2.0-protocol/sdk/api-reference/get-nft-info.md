# Get NFT Info

## Request

In order to get a NFT info on-chain, SDK provides you with a `getNFTInfo` endpoint to do so

```typescript
try {
  const testnetClient = nft2Client.getNFT2ContractMultichain('testnet');
 
  const { nft, derivedAccount } = await testnetClient.getNFTInfo(
    97,
    "0x...",  // collection address
    "123",  // token id
  );
 
  console.log(nft, derivedAccount)
} catch (e) {
  console.error(e);
}
```

## Parameters

* `chainId`: Which chain to get from.
* `collectionAddress` (string): Collection contract address.
* `tokenId` (string): NFT token ID.

## Response

{% tabs %}
{% tab title="Success" %}
```json
{
  nft: {
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
    attributes: any[];
    openAt?: Date;
    closeAt?: Date;
    royalties?: number;
    collection: Collection;
    original?: {
      collectionAddress: string;
      tokenId: string;
    };
    dataRegistry?: DataRegistry;
  };
  derivedAccount: string | null;
}
```
{% endtab %}

{% tab title="Error" %}
1. Chain not supported

```
Error: Cannot read property 'getNFTInfo' of undefined
```

2. NFT not found

```
Error: NFT not found
```
{% endtab %}
{% endtabs %}
