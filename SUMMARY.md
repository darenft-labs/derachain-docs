# Table of contents

* [Overview](README.md)

## Nodes & Validators

* [How to run a Node](nodes-and-validators/how-to-run-a-node.md)
* [Become Validator](nodes-and-validators/become-validator.md)

## NFT2.0 Protocol

* [Introduction](nft2.0-protocol/introduction.md)
* [Architecture](nft2.0-protocol/architecture.md)
* [Concepts](nft2.0-protocol/concepts/README.md)
  * [Collection](nft2.0-protocol/concepts/collection.md)
  * [NFT2.0](nft2.0-protocol/concepts/nft2.0.md)
  * [Data Registry](nft2.0-protocol/concepts/data-registry.md)
  * [Derivative NFT](nft2.0-protocol/concepts/derivative-nft.md)
  * [Derived Account](nft2.0-protocol/concepts/derived-account.md)
  * [Token Bound Account (aka TBA)](nft2.0-protocol/concepts/token-bound-account-aka-tba.md)
* [Smart Contracts](nft2.0-protocol/smart-contracts/README.md)
  * [Interfaces](nft2.0-protocol/smart-contracts/interfaces/README.md)
    * [Factory](nft2.0-protocol/smart-contracts/interfaces/factory.md)
    * [Dynamicity](nft2.0-protocol/smart-contracts/interfaces/dynamicity.md)
    * [Derivability](nft2.0-protocol/smart-contracts/interfaces/derivability.md)
    * [Cross chain ability](nft2.0-protocol/smart-contracts/interfaces/cross-chain-ability.md)
  * [Use cases](nft2.0-protocol/smart-contracts/use-cases/README.md)
    * [Create collection](nft2.0-protocol/smart-contracts/use-cases/create-collection.md)
    * [Mint NFT2.0](nft2.0-protocol/smart-contracts/use-cases/mint-nft2.0.md)
    * [Create Data registry](nft2.0-protocol/smart-contracts/use-cases/create-data-registry.md)
    * [Write onchain data](nft2.0-protocol/smart-contracts/use-cases/write-onchain-data.md)
    * [Retrieve onchain data](nft2.0-protocol/smart-contracts/use-cases/retrieve-onchain-data.md)
    * [Mint Derivative NFT2.0](nft2.0-protocol/smart-contracts/use-cases/mint-derivative-nft2.0.md)
    * [Create TBA](nft2.0-protocol/smart-contracts/use-cases/create-tba.md)
* [SDK](nft2.0-protocol/sdk/README.md)
  * [Setup](nft2.0-protocol/sdk/setup/README.md)
    * [Create Console Account](nft2.0-protocol/sdk/setup/create-console-account.md)
    * [Manage API key](nft2.0-protocol/sdk/setup/manage-api-key.md)
    * [Set up metadata schema](nft2.0-protocol/sdk/setup/set-up-metadata-schema.md)
    * [Initialize the SDK](nft2.0-protocol/sdk/setup/initialize-the-sdk.md)
  * [API reference](nft2.0-protocol/sdk/api-reference/README.md)
    * [Get List Collection](nft2.0-protocol/sdk/api-reference/get-list-collection.md)
    * [Get List Collection By Owner](nft2.0-protocol/sdk/api-reference/get-list-collection-by-owner.md)
    * [Get Collection Info](nft2.0-protocol/sdk/api-reference/get-collection-info.md)
    * [Get List NFT By Collection](nft2.0-protocol/sdk/api-reference/get-list-nft-by-collection.md)
    * [Get List NFT By Owner](nft2.0-protocol/sdk/api-reference/get-list-nft-by-owner.md)
    * [Get List Derivative NFT By Original](nft2.0-protocol/sdk/api-reference/get-list-derivative-nft-by-original.md)
    * [Get NFT Info](nft2.0-protocol/sdk/api-reference/get-nft-info.md)
    * [Get List Data Registry](nft2.0-protocol/sdk/api-reference/get-list-data-registry.md)
    * [Get Data Registry By Owner](nft2.0-protocol/sdk/api-reference/get-data-registry-by-owner.md)
    * [Get Data Registry Info](nft2.0-protocol/sdk/api-reference/get-data-registry-info.md)
    * [Get NFT onchain data](nft2.0-protocol/sdk/api-reference/get-nft-onchain-data.md)
    * [Get NFT protocol-scoped onchain data](nft2.0-protocol/sdk/api-reference/get-nft-protocol-scoped-onchain-data.md)
    * [Get User Freemint Info](nft2.0-protocol/sdk/api-reference/get-user-freemint-info.md)
    * [Get Claim Token Uri Info](nft2.0-protocol/sdk/api-reference/get-claim-token-uri-info.md)
    * [Upload JSON Uri Data To IPFS](nft2.0-protocol/sdk/api-reference/upload-json-uri-data-to-ipfs.md)
    * [Generate Presigned URL To Upload Image (IPFS)](nft2.0-protocol/sdk/api-reference/generate-presigned-url-to-upload-image-ipfs.md)
    * [Utility Functions](nft2.0-protocol/sdk/api-reference/utility-functions.md)
* [App guide](nft2.0-protocol/app-guide/README.md)
  * [NFT2Scan](nft2.0-protocol/app-guide/nft2scan/README.md)
    * [Create Collection](nft2.0-protocol/app-guide/nft2scan/create-collection.md)
    * [Mint NFT2.0](nft2.0-protocol/app-guide/nft2scan/mint-nft2.0.md)
    * [Mint Derivative NFT2.0](nft2.0-protocol/app-guide/nft2scan/mint-derivative-nft2.0.md)
  * [NFT2Console](nft2.0-protocol/app-guide/nft2console/README.md)
    * [Create Dapp](nft2.0-protocol/app-guide/nft2console/create-dapp.md)
    * [Register data schema](nft2.0-protocol/app-guide/nft2console/register-data-schema.md)
    * [Manage API keys](nft2.0-protocol/app-guide/nft2console/manage-api-keys.md)
    * [Manage onchain data](nft2.0-protocol/app-guide/nft2console/manage-onchain-data.md)
* [References](nft2.0-protocol/references/README.md)
  * [Links](nft2.0-protocol/references/links.md)

## Smart Contracts

* [EVM compatibility](smart-contracts/evm-compatibility.md)
* [Hardhat](smart-contracts/hardhat.md)
* [Account Abstraction](smart-contracts/account-abstraction.md)
* [SubQuery](smart-contracts/subquery.md)

## Bridge

* [Introduction](bridge/introduction.md)
* [Bridge Token](bridge/bridge-token.md)
* [Bridge NFT](bridge/bridge-nft.md)

## Staking

* [Introduction](staking/introduction.md)
* [Validate](staking/validate.md)
* [Delegate](staking/delegate.md)
