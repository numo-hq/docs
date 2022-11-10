# Payoff Replication

## Constructing a trading function

The same as any AMM, “replicating” refers to the method for deriving the trading function so that the portfolio of tokens it is holding follows a desired payoff. Exactly this is proved by Angeris in _Replicating Market Makers_. This research introduced the notion that **an AMM can replicate a derivative** with the liquidity providers exposed to the replicated derivative payoff.

So even if there is no on-chain market for covered calls or other types of exotic financial instruments, an AMM could replicate the payoff of one, and expose the liquidity provider to the same upside and downsides as if they were holding the instrument.

> _A liquidity provider is a fractional owner in the AMM via an LP share. By owning the LP share, the liquidity provider holds a portfolio of tokens managed by the trading function of the AMM. The LP share, therefore, has a payoff. For Uniswap LPs, the returns follow a covered call strategy that dramatically reduces the value of the portfolio as volatility increases and price decreases._

Unfortunately, **AMMs can only replicate concave payoffs without leverage.** So the type of derivatives that are replicable as an AMM is limited. In theory, if the payoff of a Uniswap LP share is a short option, then by lending it out, the payoff gets inverted to a long option on the underlying assets.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

