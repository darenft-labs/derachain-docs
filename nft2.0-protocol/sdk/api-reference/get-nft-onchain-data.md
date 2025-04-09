# Get NFT onchain data

## Request

In order to get metadata of NFT writen on data registry, SDK provides you with a `getNFTMetaData` endpoint to do so

```typescript
try {
  const mainnetClient = nft2Client.getNFT2DataRegistryMultichain('mainnet');
 
  const nftMetaDatas = await mainnetClient.getNFTMetaData(
    43114,
    "0x...",  // collection address
    "123",   // token ID
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
Array<{
  providerAddress: string;
  name: string;
  description: string;
  url: string;
  chainId: number;
  walletAddress: string;
  registryUrl: string | null;
  registeredAt: Date | null;
  schemas: {
    name: string;
    jsonSchema: object;
  };
  collectionSchemas: {
    name: string;
    jsonSchema: object;
  }[];
  metadatas: Array<{
    <key>: <value>
  }>;
}>
}
```
{% endtab %}

{% tab title="Error" %}
1. Chain not supported

```
Error: Cannot read property 'getNFTMetaData' of undefined
```

2. Dapp schema not found:

```
Error: Schema of dapp 0x... not found
```
{% endtab %}
{% endtabs %}
