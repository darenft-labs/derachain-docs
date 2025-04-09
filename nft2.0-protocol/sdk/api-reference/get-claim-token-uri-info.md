# Get Claim Token Uri Info

## Request

In order to get claim token uri info of an NFT, SDK provides you with a `getClaimTokenUriInfo` endpoint to do so

```typescript
try {
  const apiProtocol = nft2Client.getAPIService();
 
  const claimUriInfo = await apiProtocol.getClaimTokenUriInfo(
    56,  // chain id
    '0x...', // collection address
    '123', // token id
  );
 
  console.log(claimUriInfo)
} catch (e) {
  console.error(e);
}
```

## Parameters

* `chainId` (number): Chain ID.
* `collectionAddress` (string): Collection contract address.
* `tokenId` (string | number): NFT token ID.

## Response

{% tabs %}
{% tab title="Success" %}
```json
{
  tokenId?: string;
  tokenUri?: string;
  tokenUriIPFS?: string;
  leaf?: string;
  proof?: Array<string>;
}
```
{% endtab %}

{% tab title="Error" %}
1. Chain not supported

```
Error: Cannot read property 'getClaimTokenUriInfo' of undefined
```
{% endtab %}
{% endtabs %}
