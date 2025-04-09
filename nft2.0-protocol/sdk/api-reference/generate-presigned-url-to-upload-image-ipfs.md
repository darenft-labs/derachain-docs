# Generate Presigned URL To Upload Image (IPFS)

## Request

In order to get a presigned url to upload image to IPFS, SDK provides you with a `generatePresignedImage` endpoint to do so

```typescript
try {
  const apiProtocol = nft2Client.getAPIService();
 
  const presignedList = await apiProtocol.generatePresignedImage({
    files: [
      {
        fileName: 'file1.png',
        mimeType: 'image/png',
      },
      {
        fileName: 'file2.jpeg',
        mimeType: 'image/jpeg',
      },
      ...
    ]
  });
 
  console.log(presignedList)
} catch (e) {
  console.error(e);
}
```

## Parameters

* Params type: `PresignImageData`
* `files` (Array): Array of presign image metadata (fileName and mimeType).

<mark style="color:red;">**(!)**</mark> <mark style="color:yellow;">To ensure IPFS service performance and avoid rate limit when upload files, size of array files must be <= 50.</mark>

<mark style="color:red;">**(!)**</mark> <mark style="color:yellow;">Image mimeType only support in \["image/png", "image/jpeg", "image/svg+xml"]</mark>

## Response

{% tabs %}
{% tab title="Success" %}
```json
{
  urls: [
    "https://nft2-protocol.s3.filebase.com/file1-xxx.png?SIGNED_DATA&x-id=PutObject",
    "https://nft2-protocol.s3.filebase.com/file2-xxx.jpeg?SIGNED_DATA&x-id=PutObject",
    ...
  ];
}
```
{% endtab %}

{% tab title="Error" %}
```
Maybe some HTTP Exception
```
{% endtab %}
{% endtabs %}

## Using presigned URL to upload image to S3

```typescript
try {
  const presignedUrl = "..." // get from generatePresignedImage
  const file = "..." // file object or data arraybuffer
 
  const response = await axios.put(presignedUrl, file, {
    headers: {
      "Content-Type": file.type || "image/png", // mimeType
    },
  })
 
  const imageData = {
    image_name: file.name,
    image_cid: response.headers?.["x-amz-meta-cid"], // CID of image on IPFS
  }
 
  console.log(imageData)
} catch (e) {
  console.error(e);
}
```

