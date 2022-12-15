# FAQ

## What is an automated market maker (AMM)?

An automated market maker (AMM) is an overarching term used to describe an automated system that keeps a portfolio of assets weighted according to a desired strategy, or invariant. Uniswap popularized the automated market maker with the constant product invariant where x \* y = k, keeping the balance of two reserves are equal in value. Their simplicity makes them well suited for the blockchain and dominate the decentralized exchange or "DEX" market.

## What is a liquidity provider and LP share?&#x20;

A liquidity provider is a single party that rents out their capital to an AMM. In return for renting their capital, liquidity providers receive an LP share, or token, as a receipt. LP shares often earn some fees or yield pro-rata when their capital is utilized for trading. In several papers by Angeris et. al., it has been shown that LP shares mimic the payoff of a put option.

## What is a replicating market maker?

A replicating market maker is nothing different from an automated market maker, except for an innovation in deriving the invariant. Every invariant corresponds to a portfolio value that gives the value of a LP share for a given exchange rate. Traditionally, AMMs were designed with a given invariant and the portfolio value function is calculated from it. Replicating market makers start with a portfolio value that is "replicated" and the trading invariant is constructed from it. In this case the LP share of an AMM becomes a portfolio of assets that replicates a derivative payoff such as options.

## What are perpetual options?

Perpetual options are a combination of the perpetual future, the most traded crypto derivative, and the option, which is the most traded traditional derivative. The idea was introduced by Paradigm in [this Power Perp research paper](https://www.paradigm.xyz/2021/08/power-perpetuals). In short, they replicate a price^2 which is always better than 2x leverage for traders.

## What are flash swaps?

Flash swaps and flash loans are a native financial transaction that is only available on a blockchain. Flash transactions let you borrow tokens without any collateral as long as you pay it back plus some fee by the end of the transaction. If the debt is not paid back, the transaction is invalid and will revert.

## Does Numoen have a token?

No.

{% hint style="info" %}
So for a BTC/USDC Numoen Option, the squared exposure falls on BTC but the funding is paid in USDC.&#x20;
{% endhint %}
