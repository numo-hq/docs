# Pricing LP Tokens

When someone provides liquidity to the protocol, they receive a fractional share of the AMM called a LP share. Formally this user is known as a liquidity provider; a single party that rents out their capital to an AMM. In return for renting their capital, liquidity providers receive an LP share that represents their capital proportional to everyone else. And earns fees or some yield pro-rata when their capital is utilized for trading.&#x20;

## LP Share Redemptions

Unlike in the replicating monotonic payoff paper that initially describes the design a capped power trading function, the LP share is whole in its entirety. In that system where the shares are split, the long payoff of the speculative is given to the holder of the base, and the short is holding the speculative, receiving funding in the base asset. For our use case, that mechanism is susceptible to an internal oracle flash attack.



