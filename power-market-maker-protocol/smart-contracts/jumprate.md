---
description: >-
  The jump rate contract is abstract and inherited by lendgine. They are
  separated for readability.
---

# JumpRate

## Code

[`JumpRate.sol`](https://github.com/Numoen/pmmp/blob/main/src/core/JumpRate.sol)

## Read-only functions

### kink

```solidity
function kink() external view returns (uint256 kink);
```

Returns the kink used in the jump rate model.

### multiplier

```solidity
function multiplier() external view returns (uint256 multiplier);
```

Returns the multiplier used in the jump rate model.

### jumpMultiplier

```solidity
function jumpMultiplier() external view returns (uint256 jumpMultiplier);
```

Returns the jump multiplier used in the jump rate model.

### getBorrowRate

```solidity
function getBorrowRate(uint256 borrowedLiquidity, uint256 totalLiquidity) external view returns (uint256 rate);
```

Computes the borrow rate based on liquidity utilization in the jump rate model.

### getSupplyRate

```solidity
function getSupplyRate(uint256 borrowedLiquidity, uint256 totalLiquidity) external view returns (uint256 rate);
```

Computes the supply rate based on liquidity utilzation in the jump rate model.
