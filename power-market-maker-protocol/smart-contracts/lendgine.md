---
description: Inherits pair, jump rate, and immutable state.
---

# Lendgine

## Code

[`Pair.sol`](https://github.com/Numoen/pmmp/blob/main/src/core/Pair.sol)

## Events

### Mint

```solidity
event Mint(address indexed sender, uint256 collateral, uint256 shares, uint256 liquidity, address indexed to);
```

Emitted when a Power token is minted.

### Burn

```solidity
event Burn(address indexed sender, uint256 collateral, uint256 shares, uint256 liquidity, address indexed to);
```

Emitted when a Power Token is burned.

### Deposit

```solidity
event Deposit(address indexed sender, uint256 size, uint256 liquidity, address indexed to);
```

Emitted when liquidity is deposited.

### Withdraw

```solidity
event Withdraw(address indexed sender, uint256 size, uint256 liquidity, address indexed to);
```

Emitted when liquidity is withdrawn.

### AccrueInterest

```solidity
event AccrueInterest(uint256 timeElapsed, uint256 collateral, uint256 liquidity);
```

Emitted when interest is accrued.

### AccruePositionInterest

```solidity
event AccruePositionInterest(address indexed owner, uint256 rewardPerPosition);
```

Emitted when interested is accrued from a position.

### Collect

```solidity
event Collect(address indexed owner, address indexed to, uint256 amount);
```

Emitted when interest is collected from a liquidity position.

## Errors

### InputError

```solidity
error InputError();
```

Occurs when invalid inputs are passed to any function.

### CompleteUtilizationError

```solidity
error CompleteUtilizationError();
```

Occurs when liquidity is being withdraw either by a position being withdrawn or liquidity being borrowed but the liquidity is fully being borrowed.

### InsufficientInputError

```solidity
error InsufficientInputError();
```

Occurs when not enough input is sent for how much output was specified.

### InsufficientPositionError

```solidity
error InsufficientPositionError();
```

Occurs when an accounts attempts to withdraw a larger position than they have.

## Read-only functions

### positions

```solidity
function positions(address) external view returns (uint256, uint256, uint256);
```

Returns the makeup of a position.

### totalPositionSize

```solidity
function totalPositionSize() external view returns (uint256);
```

Returns the total amount of liquidity positions minted multiplied by 1 ether.

### totalLiquidityBorrowed

```solidity
function totalLiquidityBorrowed() external view returns (uint256);
```

Returns the total amount of liquidity that is currently borrowed by Power Token holders multiplied by 1 ether.

### rewardPerPositionStored

```solidity
function rewardPerPositionStored() external view returns (uint256);
```

Returns the current amount of interest that each liquidity position has earned since inception multiplied by 1 ether.

### lastUpdate

```solidity
function lastUpdate() external view returns (uint256);
```

Returns the last unix timestamp that the interest was accrued at.

### convertLiquidityToShare

```solidity
function convertLiquidityToShare(uint256 liquidity) external view returns (uint256);
```

Converts amount of liquidity borrowed to shares of Power Tokens.

### convertShareToLiquidity

```solidity
function convertShareToLiquidity(uint256 shares) external view returns (uint256);
```

Converts shares of Power Tokens to amount of liquidity borrowed.

### convertCollateralToLiquidity

```solidity
function convertCollateralToLiquidity(uint256 collateral) external view returns (uint256);
```

Converts collateral to liquidity.

### convertLiquidityToCollateral

```solidity
function convertLiquidityToCollateral(uint256 liquidity) external view returns (uint256);
```

Converts liquidity to collateral.

## State-changing functions

### mint

```solidity
function mint(address to, uint256 collateral, bytes calldata data) external returns (uint256 shares);
```

Mints a Power Token by providing token1 as collateral and borrowing a proportional amount of liquidity.

### burn

```solidity
function burn(address to, bytes calldata data) external returns (uint256 collateral);
```

Burns a Power Token by minting the required liquidity and unlocking the collateral. The amount of Power Token shares to be burned is specified by transferring that amount to this contract before calling it.

### deposit

```solidity
function deposit(address to, uint256 liquidity, bytes calldata data) external returns (uint256 size);
```

Provide liquidity to the underlying automated market maker.

### withdraw

```solidity
function withdraw(address to, uint256 size) external returns (uint256 amount0, uint256 amount1, uint256 liquidity);
```

Withdraw liquidity from the underlying automated market maker.

### accrueInterest

```solidity
function accrueInterest() external;
```

Accrues global interest by decreasing the total amount of liquidity owed by borrowers and rewarding lenders with the borrowers collateral.

### accruePositionInterest

```solidity
function accruePositionInterest() external;
```

Accrues interest for the callers liquidity position.

### collect

```solidity
function collect(address to, uint256 collateralRequested) external returns (uint256 collateral);
```

Collects the interest that has been gathered to the callers liquidity position.
