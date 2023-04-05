# Smart Contracts

[Source code](https://github.com/numoen/pmmp)

PMMP is a system of two sets of smart contracts. Core contracts implement critical accounting logic. Periphery contracts interact with core contracts with some extra safety checks and ease-of-use functionality.

## Core

The core consists of one factory contract and many lendgines, which the factory is responsible for creating and indexing. These contracts are designed to be as simple and minimal as possible. The smaller surface area is easier to reason about and more functionally elegant. The biggest upside of this design is the fact that the core logic is extensible to new use cases that may have not be imagined when it was implemented. One downside, however, is the fact that the core contracts are somewhat user-unfriendly. In fact, interacting directly with the core contracts is not recommended and instead a periphery contract should be used.

### Factory

[Reference documentation](./#factory)

The factory is responsible for create and maintain references to lendgines. It only allows for one lendgine for each unique set of invariant parameters.

### Pair

[Reference documentation](./#pair)

Pairs implement the accounting logic for the underlying automated market maker behind PMMP. This contract is abstract, meaning that it is not directly deployable. Instead, it is inherited by a lendgine. Pair is functionally the same as a UniswapV2 pool, with mint, burn, and swap functionality, except that the invariant is the capped power invariant instead of the constant product invariant.

### Lendgine

[Reference documentation](./#lendgine)

Lendgines have the primary purpose of allowing for borrowing the liquidity provider shares and handling interest payment between liquidity suppliers and liquidity borrowers. Lendgines take advantage of the fact that the underlying token balances per liquidity are bounded. Any amount above this bound can be used as collateral to borrow liquidity and therefore be always over-collateralized and never at risk of liquidation. Lendgines hold this invariant and don't allow for liquidations in any case.

## Periphery

The periphery contracts consists of a lendgine router and a liquidity manager, both meant to make interacting with core contracts safer and more user friendly. Because of PMMP's permission-less nature, periphery contracts have no special privileges with core and are completely replaceable by other periphery contracts with possible a different set of features.

### LendgineRouter

[Reference documentation](./#lendginerouter)

The lendgine router allows for easy minting and burning of Power Tokens. It contains logic for general actions such as handling WETH, supporting EIP-2612 tokens, slippage checks, and staleness checks. More specifically, the lendgine router allows for maximum leverage on Power Tokens by facilitating the borrowing of liquidity, and selling the underlying tokens into more collateral to borrow more liquidity.

### LiquidityManager

[Reference documentation](./#liquiditymanager)

The liquidity manager custodies liquidity positions and fully supports adding and removing liquidity from a lendgine. It also contains the same ease-of-use features found in lendgine router.

