---
description: Borrowers of LP tokens must pay lenders of LP tokens.
---

# Funding Rates

## Jump rate model

To determine the interest rate, the jump rate model introduced by [Compound](https://docs.compound.finance/interest-rates/).

Utilization is the proportion of LP tokens that are borrowed. Borrow and supply rates are a function of utilization. Each model has a kink rate and above this rate interest rates increase more rapidly.

## Numoen parameters

In On-chain Volatility and Uniswap V3 by Lambert (2021), it is demonstrated that LP positions are analogous selling an option and pricing follows a Geometric Brownian Motion. Using the liquidity on token pairs on Uniswap V3, we have derived the on-chain historical implied volatility, σ for each token pair. Jump rate parameters are found by taking the square root of the quotient of daily volume α over the tick liquidity β multiplied by the fee tier φ \* 2. The equation is as follows:&#x20;

$$
σ = 2φ √ α β (6)
$$

So using the most recent data on the most liquid pairs on the .3% fee tier, we estimate 105.1% to be the average implied volatility and used that to determine our parameters.

<table><thead><tr><th>Variable</th><th>Value</th><th data-hidden></th></tr></thead><tbody><tr><td>Kink</td><td>.8</td><td></td></tr><tr><td>Multiplier</td><td>1.375</td><td></td></tr><tr><td>Jump multiplier</td><td>44.5</td><td></td></tr></tbody></table>
