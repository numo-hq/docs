---
description: Power tokens are created by borrowing LP tokens from liquidity providers.
---

# Power Tokens

## Creating Power Tokens

Power Tokens are a fungible asset whose leverage is constantly squared. This payoff is the same as the squeeth payoff. So if the price moves up by 2X, then your gains increase by 4X. Or if the price increases by 4X, your gains increase by 16X.

These "leveraged" tokens are created by simply borrowing LP tokens from liquidity providers. As collateral, borrowers use the speculative token as collateral. We can derive an amount of speculative tokens such that the value of the speculative tokens is always greater than or equal to the value of the borrowed LP tokens.

Because there are no fees associated with the underlying AMM, LP tokens never go above their value and liquidations are impossible.

<figure><img src="../.gitbook/assets/Numoen Position Values (1).png" alt=""><figcaption></figcaption></figure>

Traders want these tokens because they have convexity. This means that relative to a 2x perpetual future, when prices go up, leverage tokens go up more, and when prices go down, leverage tokens go down less.

For this convexity, borrowers must pay a funding rate to liquidity providers. The funding is taken as a portion of their position, so the collateral and debt value go down simultaneously.
