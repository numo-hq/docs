---
description: Power Market Maker Protocol
---

# PMMP

## Automated market makers

Numoen uses an automated market maker under the hood. Popularized by Uniswap, and automated market maker is a very simple form of exchange that rejects or accepts trades depending on whether the trade satisfies the trading invariant. Users wishing to provide liquidity for a market can deposit to the automated market maker. They have been shown to be a really powerful way to bootstrap liquidity for any market, but the profitability for liquidity providers has been questioned.&#x20;

## Providing liquidity

Providing liquidity is the act of adding two tokens to an automated market maker. In exchange for providing liquidity, a LP token is issued to the depositor.\
\
LP tokens represent a share of the underlying pool. When a user wants to redeem their LP token, they receive the underlying tokens proportional to how much of the total LP token supply they have, not necessarily the same balances that they deposited.

## Portfolio values

A portfolio value gives the value of a LP share for a given exchange rate. The portfolio value of an AMM can be derived from the trading invariant or vice-versa.

It has been shown that portfolio values of all constant function automated market makers are nondecreasing, non-negative, and concave. This means that without external rewards, providing liquidity is always worse than holding the underlying tokens.

<figure><img src="../.gitbook/assets/Uniswap V2 Porfolio Value (2).png" alt=""><figcaption></figcaption></figure>



## Numoen Invariant

The invariant used in the Numoen core protocol is taken from a [research paper by Angeris et al](https://arxiv.org/abs/2111.13740).&#x20;

$$
\varphi(R_{1}, R_{2}) = R_{1}-\left(p_{1}-\frac{1}{2}R_{2}\right)^{2}
$$

Where p1 represents the upper bound of the exchange rate. This results in a portfolio value of:&#x20;



$$
V(p)=
    \begin{cases}
        2p*p_{1}-p^{2} & 0\le p\le p_{1}\\
        p_{1}^{2} & p > p_{1}
    \end{cases}
$$

One thing that is important to note that the two tokens are not interchangeable as in Uniswap. Swapping the two tokens in the invariant results in a different AMM.

Numoen separates the two tokens into a speculative token and a base token. In the example below, Ether is the speculative token and Marshall Rogan Inu is the base token.

<figure><img src="../.gitbook/assets/Numoen Core Portfolio Value.png" alt=""><figcaption><p>The value of a Numoen LP position with p1 as 3</p></figcaption></figure>

## Lending LP tokens

In Numoen, when minting an LP token, it is immediately lent out in a lending market.

## Payment

As previously mentioned, using two tokens to mint an LP shares without external rewards is always worse than just holding the tokens. Liquidity providers lose money when the price that they exit their position is different than the price when they enter the position. This is sometimes referred to as impermanent loss.

Uniswap makes up for this by rewarding liquidity providers with a small fee taken from traders after every trade. This makes a Uniswap LP position a long on trading volume but short on volatility.&#x20;

Numoen solves this problem a different way. There are no trading fees taken, instead liquidity providers lend out their LP tokens to options traders who are looking to borrow them. It is later shown that the funding rate that is earned from lending out is a function of implied volatility. This makes a Numoen LP position long implied volatility but short realized volatility.
