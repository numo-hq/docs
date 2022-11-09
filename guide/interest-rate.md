# Interest Rate

Hardcoded in the Numoen Core contracts is a "_jump rate_" based interest curve. This sets the interest rate on each Numoen LP position. Used by the most popular money markets today, the jump rate model is a statically parameterized curve that dictates an interest rate based on utilization of funds. The jump rate model determines the funding rate that must be paid from the holders of perpetual options to liquidity providers.&#x20;

In On-chain Volatility and Uniswap V3 by Lambert (2021), it is demonstrated that LP positions are analogous selling an option and pricing follows a Geometric Brownian Motion. Using the liquidity on token pairs on Uniswap V3, we have derived the on-chain historical implied volatility, σ for each token pair. Jump rate paratmers are found by taking the square root of the quotient of daily volume α over the tick liquidity β multiplied by the fee tier φ \* 2. The equation is as follows:&#x20;

$$
σ = 2φ √ α β (6)
$$

So using the most recent data on the most liquid pairs on the .3% fee tier, we estimate 105.1% to be the average implied volatility and used that to determine our parameters. The borrow rate between liquidity providers and perpetual options holders is calculated as multiplier ∗ min(Ua, kink) + jumpMultiplier max(0, Ua − kink)

| Type    | Variable       | Number      |
| ------- | -------------- | ----------- |
| uint256 | kink           | .8 ether    |
| uint256 | multiplier     | 1.375 ether |
| uint256 | JumpMultiplier | 44.5 ether  |
