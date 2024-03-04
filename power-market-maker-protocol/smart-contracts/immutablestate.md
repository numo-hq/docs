---
description: >-
  The immutable state smart contract is abstract and inherited by lendgine. They
  are separated for readability.
---

# ImmutableState

## Code

[`ImmutableState.sol`](https://github.com/Numoen/pmmp/blob/main/src/core/ImmutableState.sol)

## State-changing functions

### factory

```solidity
function factory() external view returns (address);
```

Returns the address of the factory that deployed this lendgine.

### token0

```solidity
function token0() external view returns (address);
```

The address of the ERC20 token0.

### token1

```solidity
function token1() external view returns (address);
```

The address of the ERC20 token1.

### token0Scale

```solidity
function token0Scale() external view returns (uint256);
```

The scale required to make token0 18 decimals. In extreme cases it can be set differently for more precision.

### token1Scale

```solidity
function token1Scale() external view returns (uint256);
```

The scale required to make token1 18 decimals. In extreme cases it can be set differently for more precision.

### upperBound

```solidity
function upperBound() external view returns (uint256);
```

The price at which the underlying liquidity pool is swapped entirely into token0.
