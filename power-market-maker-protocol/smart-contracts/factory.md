# Factory

## Code

[`Factory.sol`](https://github.com/Numoen/pmmp/blob/main/src/core/Factory.sol)

## Events

### LendgineCreated

```solidity
  event LendgineCreated(
    address indexed token0,
    address indexed token1,
    uint256 token0Exp,
    uint256 token1Exp,
    uint256 indexed upperBound,
    address lendgine
  );
```

Emitted each time a new lendgine is created.

## Errors

### SameTokenError

<pre class="language-solidity"><code class="lang-solidity"><strong>error SameTokenError();
</strong></code></pre>

Emitted an account attempts to create a lendgine with two of the same tokens.

### ZeroAddressError

```solidity
error ZeroAddressError();
```

Emitted when an account attempts to create a lendgine with one of the token's addresses being 0.

### DeployedError

```solidity
error DeployedError();
```

Emitted when an account attempts to create a lendgine but that exact lendgine is already created.

### ScaleError

```solidity
error ScaleError();
```

Emitted when an account attempts to create a lendgine with a token scale that is invalid.

## Read-only functions

### getLendgine

```solidity
  function getLendgine(
    address token0,
    address token1,
    uint256 token0Exp,
    uint256 token1Exp,
    uint256 upperBound
  )
    external
    view
    returns (address lendgine);
```

Returns the lendgine address for a given pair of tokens and upper bound. Returns 0 if the lendgine doesn't exist.

### parameters

```solidity
  function parameters()
    external
    view
    returns (address token0, address token1, uint128 token0Exp, uint128 token1Exp, uint256 upperBound);
```

Parameters used during lendgine creation, set transiently for on-chain computable create2 addresses.

## &#x20;State-changing functions

### createLendgine

```solidity
  function createLendgine(
    address token0,
    address token1,
    uint8 token0Exp,
    uint8 token1Exp,
    uint256 upperBound
  )
    external
    returns (address);
```

Deploys a lendgine with the supplied parameters. Transiently sets the parameters slots and clears them after creation.

