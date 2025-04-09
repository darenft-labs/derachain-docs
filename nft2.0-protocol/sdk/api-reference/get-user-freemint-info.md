# Get User Freemint Info

## Request

In order to get freemint info of an wallet address, SDK provides you with a `getFreeMintInfo` endpoint to do so

```typescript
try {
  const apiProtocol = nft2Client.getAPIService();
 
  const freemintInfo = await apiProtocol.getFreeMintInfo(
    56,  // chain id
    '0x...', // collection address
    '0x...', // campaign id
    '0x...', // user wallet
  );
 
  console.log(freemintInfo)
} catch (e) {
  console.error(e);
}
```

## Parameters

* `chainId` (number): Chain ID.
* `collectionAddress` (string): Collection contract address.
* `campaignId` (string): Campaign ID.
* `walletAddress` (string): Wallet address of user.

## Response

{% tabs %}
{% tab title="Success" %}
```json
{
  walletAddress?: string;
  amount?: string;
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
Error: Cannot read property 'getFreeMintInfo' of undefined
```
{% endtab %}
{% endtabs %}
