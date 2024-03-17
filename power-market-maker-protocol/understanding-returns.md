# Understanding Returns

## Portfolio values

A portfolio value gives the value of a LP share for a given exchange rate. The portfolio value of an AMM can be derived from the trading invariant or vice-versa.

It has been shown that portfolio values of all constant function automated market makers are nondecreasing, non-negative, and concave. This means that without external rewards, providing liquidity is always worse than holding the underlying tokens.

<figure><img src="../.gitbook/assets/Uniswap V2 Porfolio Value (2).png" alt=""><figcaption></figcaption></figure>



## PowerMaker portfolio values

The portfolio value of a PowerMaker liquidity position is shown below:

$$
V(p)=
    \begin{cases}
        2p*p_{1}-p^{2} & 0\le p\le p_{1}\\
        p_{1}^{2} & p > p_{1}
    \end{cases}
$$

<figure><img src="../.gitbook/assets/Numoen Core Portfolio Value.png" alt=""><figcaption><p>The value of a Numoen LP position with p1 as 3</p></figcaption></figure>

<figure><img src="../.gitbook/assets/Numoen Position Values (1).png" alt=""><figcaption></figcaption></figure>

