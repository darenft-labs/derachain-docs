# Get Data Registry By Owner

## Request

In order to get a data registry of an wallet (if existed), SDK provides you with a `getDataRegistryByOwner` endpoint to do so

```typescript
try {
  const testnetClient = nft2Client.getNFT2DataRegistryMultichain('testnet');
 
  const dataRegistry = await testnetClient.getDataRegistryByOwner(
    43113
    "0x..."  // user wallet 
  );
 
  console.log(dataRegistry)
} catch (e) {
  console.error(e);
}
```

## Parameters

* `chainId`: Which chain to get from.
* `ownerAddress` (string): Wallet address of owner.

## Response

{% tabs %}
{% tab title="Success" %}
```json
{
  name: string;
  description: string;
  url: string;
  chainId: number;
  providerAddress: string;
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
}
```
{% endtab %}

{% tab title="Error" %}
1. Chain not supported

```
Error: Cannot read property 'getDataRegistries' of undefined
```

2. Data registry not found

```
Error: Data registry not found
```
{% endtab %}
{% endtabs %}
