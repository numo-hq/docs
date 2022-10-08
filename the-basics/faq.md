# FAQ

## What is an Automted Market Maker?

An Automated Market Maker (AMM) is an overarching term used to describe a system where a trading function known as an invariant holds the amount of tokens it holds to some desired level. For a constant product invariant (x\*y=k), the balance of two reserves are equal in value. Making them well suited for the exchange of two assets without matching. Hence, AMMs have been popularized as decentralized exchange venues called "DEXs" on a blockchain.

## What is a Liquidity Provider and LP share?&#x20;

A liquidity provider is a single party that rents out their capital to an AMM. In return for renting their capital, liquidity providers receive an LP share that represents their capital proportional to everyone else. And earns fees or some yield pro-rata when their capital is utilized for trading. In several papers by Angeris et. al., it has been shown that LP shares mimic the payoff of a put option.

## What is a Replicating market Maker?

A replicating market maker is nothing different from an Automated Market Maker, except that it described the method "replicating" where a trading function is constructed from some desired payoff. In this case the LP share of an AMM becomes a portfolio of assets that replicates a derivative payoff such as options.

## What are Perpetual Options?

Traditionally, options are financial instruments that give a buyer the right but not the obligation to buy the underlying asset at some agreed upon price before the option to do so expires. In finance, they represent some of the most commonly traded instruments in the world and are essential to how portfolios are constructed and risk is managed. On the otherhand, options in DeFi are virtually non-existant. Perpetual options are an attempt by the Paradigm research team to bring the convexity of an options exposure to users.&#x20;

## What are Flash Swaps?

To collateralize the LP share with the perpetual call option payoff, Numoen uses a flash swap to mint the LP token.&#x20;

## Why does my perpetual option token hold two assets?

The perpetual option token is an LP share with two assets where the exposure on the speculative and the denomination is whatever the numeraire is.
