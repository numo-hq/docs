# Power Perpetual ERC-20 Token

## Basics

Each power perpetual is an ERC20 token with constant 2x leverage. As an acronym we call it **PPT**, short for Power Perpetual Token. In many ways you can view it as a wrapped option strategy that tracks the price between two underlying assets and raises it to the power of two. Because the leverage is constantly rebalancing, Power Tokens can never be liquidated. Power tokens are not traded, they are simply minted or burned, which will be explore further in a different section.

## Why would I want a Power Token?

Power Tokens are useful because they have the property of asymmetric upside. This means that relative to a 2x perpetual future, when prices go up, Power Tokens have higher returns than the future, and when prices go down, Power Token have less worse (better) returns than the future.&#x20;

## How are Power Tokens created?

Power tokens are created with a novel mechanism of borrowing LP shares. Power Tokens represent some collateral in the token that is being "longed" and some debt in LP shares, yet the position itself doesn't hold any LP shares. Power Tokens aren't bought and sold on secondary markets, instead they are minted and burned in exchange for the underlying tokens, similar to Uniswap LP positions.

## What is the cost of owning a Power Token?

All these great properties don't come for free. Power Tokens must continuously pay for borrowing liquidity. This achieved by slowly decreasing the redemption value of a Power Token such that, if prices stay the same, a Power Token today is worth more than a Power Token tomorrow. This rate is determined by some static parameters as well a how much of the supplied liquidity is being actively borrowed. This mechanism is called the Jump Rate Model.

## Power Token bounds

One downside of being fully overcollateralized is the fact that Power Tokens cannot replicate infinite payoffs. In practice, this means that above some price, the leverage is no longer constantly rebalancing and is therefore below 2x leverage. This price is parameterized as the upper bound. It is important to note that Power Tokens are path independent and will regain constant leverage once prices go below the upper bound.

