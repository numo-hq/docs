# Interest Rate

Hardcoded in the Numoen Core contracts in a jump rate model that sets the interest rate on each Uniswap LP position. Used by the most popular money markets today, the jump rate model is a statically parameterized curve that dictates an interest rate based on utilization of funds. The jump rate model determines the funding rate that must be paid from the holders of perpetual options to liquidity providers. In On-chain Volatility and Uniswap V3 by Lambert (2021), it is demon- strated that LP positions are analogous selling an option and pricing follows a 4 Geometric Brownian Motion. Using the liquidity on token pairs on Uniswap V3, we can derive the on-chain implied volatility, σ for each token pair. Jump rate paratmers are found by taking the square root of the quotient of daily volume α over the tick liquidity β multiplied by the fee tier φ \* 2. The equation is as follows:&#x20;

$$
σ = 2φ √ α β (6)
$$



So using the most recent data on the most liquid pairs on the .3% fee tier, we estimate 105.1% to be the average implied volatility. uint256 kink .8 ether uint256 multiplier 1.375 ether uint256 jumpMultiplier 44.5 ether The borrow rate between liquidity providers and perpetual options holders is calculated as multiplier ∗ min(Ua, kink) + jumpMultiplier max(0, Ua − kink)

| Type    | Variable       | Number      |
| ------- | -------------- | ----------- |
| uint256 | kink           | .8 ether    |
| uint256 | multiplier     | 1.375 ether |
| uint256 | JumpMultiplier | 44.5 ether  |



Unique to the Numoen protocol is the interest rate model. As it stands, the user defines the rate that they want in return for lending out their capital. This mechanism has been created as a more fluid way for interest rate discovery between the makers and takers. We have coined this as the ** **_**concentrated Interest rate model**_**.**&#x20;

As more takers enter the pool, they greedily select the capital with the lowest interest rate. Negative rates are possible when a maker's position is more demanded than the takers. This user defined interest rate curve improves capital utilization and doesn't rely on a third party to statically choose a model based on historical data. \newline This architecture results in a few very desirable qualities. Takers can always redeem their token for its underlying from the market. Meaning there will never be a liquidity crunch on the synthetic token as people exit their position. A participant can also mint a new taker token whenever the utilization, $$U_{0}$$ of the maker's funds is less than 100%, $$U_{0} < 100$$. The same is true for makers: makers can redeem their tokens for the underlying asset whenever the utilization is less than 100%.



<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
