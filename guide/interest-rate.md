# Interest Rate

Unique to the Numoen protocol is the interest rate model. As it stands, the user defines the rate that they want in return for lending out their capital. This mechanism has been created as a more fluid way for interest rate discovery between the makers and takers. We have coined this as the ** **_**concentrated Interest rate model**_**.**&#x20;

As more takers enter the pool, they greedily select the capital with the lowest interest rate. Negative rates are possible when a maker's position is more demanded than the takers. This user defined interest rate curve improves capital utilization and doesn't rely on a third party to statically choose a model based on historical data. \newline This architecture results in a few very desirable qualities. Takers can always redeem their token for its underlying from the market. Meaning there will never be a liquidity crunch on the synthetic token as people exit their position. A participant can also mint a new taker token whenever the utilization, $$U_{0}$$ of the maker's funds is less than 100%, $$U_{0} < 100$$. The same is true for makers: makers can redeem their tokens for the underlying asset whenever the utilization is less than 100%.



<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
