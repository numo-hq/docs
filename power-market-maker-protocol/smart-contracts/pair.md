---
description: >-
  The pair smart contract is abstract and inherited by lendgine. They are
  separated for readability.
---

# Pair

## Code

[`Pair.sol`](https://github.com/Numoen/pmmp/blob/main/src/core/Pair.sol)

## Events

### Mint

```solidity
event Mint(uint256 amount0In, uint256 amount1In, uint256 liquidity);
```

Emitted when liquidity is minted in the pair.

### Burn

```solidity
event Burn(uint256 amount0Out, uint256 amount1Out, uint256 liquidity, address indexed to);
```

Emitted when liquidity is burned in the pair.

### Swap

```solidity
event Swap(uint256 amount0Out, uint256 amount1Out, uint256 amount0In, uint256 amount1In, address indexed to);
```

Emitted when a swap occurs in the pair.

## Errors

### InvariantError

```solidity
error InvariantError();
```

Occurs when an account takes an action and the resulting pair balances don't satisfy the invariant.

### InsufficientOutputError

```solidity
error InsufficientOutputError();
```

Occurs when the output of an actions is 0.

## Read-only functions

### reserve0

```solidity
function reserve0() external view returns (uint120);
```

Returns the balance of the token0 reserves held in the automated market maker.

### reserve1

```solidity
function reserve1() external view returns (uint120);
```

Returns the balance of the token1 reserves held in the automated market maker.

### totalLiquidity

```solidity
function totalLiquidity() external view returns (uint256);
```

Returns the total amount of liquidity currently held in the automated market maker.

### invariant

```solidity
function invariant(uint256 amount0, uint256 amount1, uint256 liquidity) external view returns (bool);
```

Implements the capped power invariant and returns true if the invariant is satisfied by the parameters.

## State-changing functions

### swap

```solidity
function swap(address to, uint256 amount0Out, uint256 amount1Out, bytes calldata data) external;
```

Swaps tokens. Sends the amounts out to the `to` address. A callback is called and `data` is passed back.

### mint

```solidity
function mint(uint256 liquidity, bytes calldata data) internal;
```

Mints liquidity. A calback is called and data is passed back.

### burn

```solidity
function burn(address to, uint256 liquidity) internal returns (uint256 amount0, uint256 amount1);
```

Burns liquidity.

