# Providing Liquidity

## Introduction

Each underlying market on PMMP contains an underlying liquidity pool, a set of two reserves that accepts or rejects trades based on a trading invariant. The price exposed by the pool depends on the balances of the reserves. When liquidity providers add liquidity to a pool, they deposits tokens proportional to the current price.

## Pool tokens

As a receipt for adding liquidity, token known as liquidity provider tokens are given as a receipt. These tokens represent a given liquidity provider's contribution to a pool. The proportion of the pool's liquidity provided determines the number of liquidity tokens the provider receives.

To retrieve the underlying liquidity, liquidity providers must "burn" their liquidity tokens, effectively exchanging them for their portion of the liquidity pool.

## Incentives for providing liquidity

Liquidity providers suffer from a phenomenon known as impermanent loss, which occurs when the price is different when you add and remove liquidity. Typically, to make up for impermanent loss, an automated market maker would charge a fee on trades. PMMP takes a different approach, lending out the liquidity and charging interest. This is better for many reasons, but in summary it allows for a variable rate of return rather than fixed and creates a more efficient market for liquidity providers.

