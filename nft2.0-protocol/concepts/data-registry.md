---
description: Concept of Data Registry in protocol
---

# Data Registry

Data Registry is the cornerstone of NFT2.0 Protocol, providing data storage and serving as a database for on-chain data of NFT. It is designed to support both novel NFT2.0 items and legacy NFT items. Data Registry enables protocol to introduce unprecedented attributes to NFT, including: dynamicity, derivability which we will examine in detail below.

## Dynamicity

The notion of dynamicity implies the ability of NFT to evolve during its life cycle, and the associated data that represents the state of the NFT. For example, player in a RPG game can level up his hero NFT  by complete the mission or quest ingame, thus inherently gain the value of NFT itself. Should the level of NFT is stored onchain, it can be lookuped permisionlessly by any other Dapps or Smart contracts, preserving NFT's value across blockchain space.

## Derivability

Derivability implies the ability of NFT to derive to a derivative assets, providing the derivative assets inherit whole or partial values of the underlying, in a limited time period. Derivative NFTs can be trade in the secondary market, in the same manner as the underlyings. The first use case of derivative NFTs which protocol introduces is Rental market. In particular, NFT owner specifies which data and time period that derivative NFT inherits from the underlying NFT.

## Technical design

Data Registry is designed in a hashtable pattern, comprised of multiple key / values pairs.

Key is hashed value of original property name.

For example: if property is LEVEL, then key is determined like so:

```solidity
bytes32 key = keccak256("LEVEL");
```

Actually, it equals `0xaa7ef1d11da7ae8b20914b6a200903893345e4c731dcaa7e093a709901ae1ec9`

Value is encoded bytes of original value, utilizing a encoding scheme.

In the current version, we are utilizing ABI encoding scheme to encode value, but the proposal for a much more efficient encoding scheme (CBOR) is intensively researched and experimented, and will replace the current encoding scheme in the future.

```solidity
bytes value = abi.encode("original value");
```

For example: if the original value is 10, then the encoded value will be `0x000000000000000000000000000000000000000000000000000000000000000a`

The only requirement for encoding scheme is it must be compatible with both Solidity smart contracts and offchain processing.
