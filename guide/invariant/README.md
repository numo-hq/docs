# Invariant

Constant Function Market Makers (CFMMs) are a subclass of Automated Market Makers (AMM) that utilize a trading function $$\varphi$$ to maintain a desired ratio of reserves held $$R \in \boldsymbol{\mathbb{R}_+}^{n}$$ by the AMM. This creates a generalized pricing algorithm, represented as a curve that multiple agents pool liquidity to. Thereby, a liquidity provider is in effect holding a portfolio of tokens and exposed to the volatility risks of the two underlying assets. More importantly, the invariant quotes a price to an agent for some scalar quantity in a two-asset trade. This proposal $$(\Delta, \Lambda)$$ is accepted by the AMM if the trading function $$\varphi(R)$$ is unchanged, the fee $$\gamma$$ is < 1, and the amount of reserves $${R_1, R_2}$$is sufficient as described by $$\varphi({R}+\gamma\Delta-\Lambda) = \varphi(R)$$.

{% hint style="info" %}
The trading function for Numoen is as follows $$\varphi({R_1},{R_2}) = R_{1}-\left(p_{1}+\frac{-1}{2}R_{2}\right)^{2}$$
{% endhint %}

In effect the invariant produces a statically replicate curve on a concentrated constant product curve.&#x20;
