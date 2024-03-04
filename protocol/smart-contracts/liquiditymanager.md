# LiquidityManager

## Code

[`LiquidityManager.sol`](https://github.com/Numoen/pmmp/blob/main/src/periphery/LiquidityManager.sol)

## Events

### AddLiquidity

```solidity
event AddLiquidity(
  address indexed from,
  address indexed lendgine,
  uint256 liquidity,
  uint256 size,
  uint256 amount0,
  uint256 amount1,
  address indexed to
);
```

Emitted when liquidity is added to a lendgine using this position manager.

### RemoveLiquidity

```solidity
event RemoveLiquidity(
  address indexed from,
  address indexed lendgine,
  uint256 liquidity,
  uint256 size,
  uint256 amount0,
  uint256 amount1,
  address indexed to
);
```

Emitted when liquidity is removed from a lendgine using this position manager.

### Collect

```solidity
event Collect(address indexed from, address indexed lendgine, uint256 amount, address indexed to);
```

Emitted when interest is collect from a position.

## Errors

### LivelinessError

```solidity
error LivelinessError();
```

Occurs when a transaction is processed later than the deadline specified.

### AmountError

```solidity
error AmountError();
```

Occurs when output amounts aren't sufficient according to the specified minimums.

### ValidationError

```solidity
error ValidationError();
```

Occurs when a callback invocation is not valid because it is not called by a lendgine deployed by the PMMP factory.

### CollectError

```solidity
error CollectError();
```

Occurs when the amount of interest collect from the lendgine is not equal to the amount specified.

## Read-only functions

### factory

```solidity
function factory() external view returns (address);
```

Returns the address of the PMMP factory this router is connected to.

### weth

```solidity
function weth() external view returns (address);
```

Returns the address of the Wrapped Ether contract.

### positions

```solidity
function positions(address owner, address lendgine) external view returns (uint256 size, uint256 rewardPerPositionPaid, uint256 tokensOwed);
```

Returns the makeup of a position.

## State-changing functions

### addLiquidity

```solidity
function addLiquidity(AddLiquidityParams calldata params) external payable;
```

Adds liquidity to a lendgine with safety checks and records the position.

### removeLiquidity

```solidity
function removeLiquidity(RemoveLiquidityParams calldata params) external payable;
```

Removes liquidity from a lendgine with safety checks and updates the position.

### collect

```solidity
function collect(CollectParams calldata params) external payable returns (uint256 amount); 
```

Collects interest from a position with safety checks and accrues interest before collecting.
