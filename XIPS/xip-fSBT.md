---
xip: 10
title: Introduce Future SBT
description: fSBT (Future Soul Bound Token) is a type of token that has a limit on the number of transfers that can be made with it, and can be issued in advance or by a user's account to strengthen its SBT- or NFT-like characteristics, with the owner able to restrict its functions or burn it.
author: Erick You <erick@catze.xyz>
discussions-to: https://www.xdc.dev/web3isthefuture/wip-xip-proposal-introduce-future-sbt-3g1m
status: Draft
type: Standards Track
category (*only required for Standards Track): XRC
created: 2023-01-10
requires (*optional): 10
---

## Abstract
fSBT (Future Soul Bound Token) is a type of token that has a limit on the number of transfers that can be made with it, and can be issued in advance or by a user's account to strengthen its SBT- or NFT-like characteristics, with the owner able to restrict its functions or burn it.

## Motivation
A standard interface allows any tokens on XDC Network to be re-used by other applications: from wallets to decentralized exchanges.

## Specification

### Methods

**NOTES**:
 - The following specifications use syntax from Solidity `0.4.17` (or above)
 - Callers MUST handle `false` from `returns (bool success)`.  Callers MUST NOT assume that `false` is never returned!

#### name

returns the name of the token as a string


``` js
function name() public view returns (string)
```

#### symbol

returns the symbol of the token as a string


``` js
function symbol() public view returns (string)
```

#### totalSupply

Returns the total token supply.

``` js
function totalSupply() external view returns (uint256)
```

#### balanceOf

Returns the account balance of another account with address `owner`.

``` js
function balanceOf(address owner) external view returns (uint256)
```

#### transferFrom

Transfers the ownership of a given token ID to another address.

``` js
function transferFrom(address from, address to, uint256 tokenId) public
```

#### approve

Approves another address to transfer the given token ID

``` js
function approve(address to, uint256 tokenId) public
```

#### limitedTransfer

Transfers _value amount of tokens from address _from to address _to, and MUST fire the Transfer event.

The limitedTransfer method is used for a withdraw workflow, allowing contracts to transfer tokens on your behalf. This can be used for example to allow a contract to transfer tokens on your behalf and/or to charge fees in sub-currencies. The function SHOULD throw unless the _from account has deliberately authorized the sender of the message via some mechanism.

Transfers of 0 values MUST be treated as normal transfers and fire the Transfer event.

``` js
function limitedTransfer(address _from, address _to, uint256 _value) public returns (bool success)
```

#### batchRevoke

Revokes the specified tokens.

``` js
function batchRevoke(uint256[] memory _tokenIds) public returns (bool success)
```

#### batchAttest

Attests the specified tokens.

``` js
function batchAttest(uint256[] memory _tokenIds) public returns (bool success)
```

### Events

#### Transfer

MUST trigger when tokens are transferred, including zero value transfers.

A token contract which creates new tokens SHOULD trigger a Transfer event with the `_from` address set to `0x0` when tokens are created.

``` js
event Transfer(address indexed _from, address indexed _to, uint256 _value)
```

#### Approval

MUST trigger on any successful call to `approve(address _spender, uint256 _value)`.

``` js
event Approval(address indexed _owner, address indexed _spender, uint256 _value)
```

#### Revoke

MUST trigger when tokens are revoked.

``` js
event Revoke(uint256 indexed _tokenId)
```

#### Attest

MUST trigger when tokens are attested.

``` js
event Attest(uint256 indexed _tokenId)
```

#### OwnershipTransferred

MUST trigger when token ownership is transferred.

``` js
event OwnershipTransferred(uint256 indexed _tokenId, address indexed _prevOwner, address indexed _newOwner)
```

## Rationale
This document was derived heavily from [BNB Chain's BEP-179](https://github.com/bnb-chain/BEPs/pull/179) and the interface is fully compatible with BNB Chain's fSBT. This makes it easy to reuse code and tools from the Ethereum ecosystem.

## Reference Implementation
Examples of future SBTs can be used as a reference implementation, which are available at

- [CatzeLabs implementation](https://github.com/catze-labs/futureSBT/)
- [Binance Evolution Proposal](https://github.com/bnb-chain/BEPs/pull/179)

## Copyright
Copyright and related rights waived via [CC0](../LICENSE.md).