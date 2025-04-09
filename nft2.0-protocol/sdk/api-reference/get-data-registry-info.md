# Get Data Registry Info

## Request

In order to get a data registry info on-chain, SDK provides you with a `getDataRegistryInfo` endpoint to do so

```typescript
try {
  const testnetClient = nft2Client.getNFT2DataRegistryMultichain('testnet');
 
  const dataRegistry = await testnetClient.getDataRegistryInfo(
    97,
    "0x..."  // data registry contract address 
  );
 
  console.log(dataRegistry)
} catch (e) {
  console.error(e);
}
```

## Parameters

* `chainId`: Which chain to get from.
* `registryAddress` (string): Data registry contract address.

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
Error: Cannot read property 'getDataRegistryInfo' of undefined
```

2. Data registry not found

```
Error: Data registry not found
```
{% endtab %}
{% endtabs %}
