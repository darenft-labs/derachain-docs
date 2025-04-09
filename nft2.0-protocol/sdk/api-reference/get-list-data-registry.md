# Get List Data Registry

## Request

In order to get list data registry, SDK provides you with a `getDataRegistries` endpoint to do so

```typescript
try {
  const mainnetClient = nft2Client.getNFT2DataRegistryMultichain('mainnet');
 
  const { datas, total } = await mainnetClient.getDataRegistries(
    {
      limit: 20,
      offset: 0
    },
    [56, 43114]
  );
 
  console.log(datas, total)
} catch (e) {
  console.error(e);
}
```

## Parameters

* Pagination:
  * `limit` (number): Pagination limit.
  * `offset` (number): Pagination offset.
  * `sort` (`{field: 'registeredAt'; order: 'DESC' | 'ASC'}`): Optional. Only support sort on data registry deploy block. Default order DESC.
  * `filter` (`{collection: string; tokenId: string;}`): Optional. If exist, filter only data registry which is derivable for this NFT.
* `chainIds`: Which chains to get from.

## Response

{% tabs %}
{% tab title="Success" %}
```json
{
  datas: Array<{
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
  }>;
  total: number;
}
```
{% endtab %}

{% tab title="Error" %}
1. Chain not supported

```
Error: Cannot read property 'getDataRegistries' of undefined
```
{% endtab %}
{% endtabs %}
