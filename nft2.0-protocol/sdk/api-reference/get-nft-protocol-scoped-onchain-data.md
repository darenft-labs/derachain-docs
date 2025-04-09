# Get NFT protocol-scoped onchain data

## Request

In order to get protocol-scoped onchain data of NFT on a data registry, SDK provides you with a `getNFTProtocolMetaData` endpoint to do so

```typescript
try {
  const mainnetClient = nft2Client.getNFT2DataRegistryMultichain('mainnet');
 
  const nftMetaDatas = await mainnetClient.getNFTProtocolMetaData(
    56,
    "0x...",  // collection address
    "123",   // token ID
    "0x...",  // provider address
  );
 
  console.log(nftMetaDatas)
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
  metadatas: {
    key: string;
    value: any;
  }[];
  dynamicDatas: {
    name: string;
    description: string;
    image: srting;
    attributes: Array<any>;
    tokenUri: string;
    tokenUriGateway: string;
  };
}
```
{% endtab %}

{% tab title="Error" %}
1. Chain not supported

```
Error: Cannot read property 'getNFTProtocolMetaData' of undefined
```
{% endtab %}
{% endtabs %}
