# Upload JSON Uri Data To IPFS

## Request

In order to create token uri for NFT or registry uri for data registry, SDK provides you with a `uploadJSONUriInfo` endpoint to do so

```typescript
try {
  const apiProtocol = nft2Client.getAPIService();
 
  const uriList = await apiProtocol.uploadJSONUriInfo({
    items: [
      {
        name: "NFT 1 name",
        description: "NFT 1 desc",
        image: "ipfs://XXX",
        attributes: [
          { trait_type: "Level", value: 8 },
          { trait_type: "Type", value: "Monster" }
        ]
      },
      ...
    ]
  });
 
  console.log(uriList)
} catch (e) {
  console.error(e);
}
```

## Parameters

* Params type: `JsonUriMetadata`
* `items` (Array): Array of Json metadata.

<mark style="color:red;">**(!)**</mark> <mark style="color:yellow;">To ensure IPFS service performance and avoid rate limit, size of array items must be <= 100.</mark>

## Response

{% tabs %}
{% tab title="Success" %}
```json
[
  { tokenUri: "https://clouflare-ipfs.com/ipfs/XXX" },
  { tokenUri: "https://clouflare-ipfs.com/ipfs/YYY" },
  ...
]
 // with `XXX` and `YYY` is CID of URI data file store on IPFS
```
{% endtab %}

{% tab title="Error" %}
```
Maybe some HTTP Exception
```
{% endtab %}
{% endtabs %}
