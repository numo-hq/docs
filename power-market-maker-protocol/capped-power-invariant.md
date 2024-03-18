# Capped Power Invariant

The capped power invariant replicates any power perpetual payoff and was introduced in a research paper called [_Replicating Monotonic Payoffs Without Oracles._](https://arxiv.org/abs/2111.13740)

$$
\begin{equation}
    \varphi(R_{1},R_{2}) = R_{1}+p_{0}^{\alpha}-\left(p_{1}^{\left(\alpha-1\right)}+\frac{\left(1-\alpha\right)}{\alpha}R_{2}\right)^{\left(\frac{\alpha}{\alpha-1}\right)}
\end{equation}
$$

## PowerMaker1

The capped power-2 invariant is the trading invariant for squared, "Squeeth" exposure.

$$
\varphi(R_{1}, R_{2}) = R_{1}-\left(p_{1}-\frac{1}{2}R_{2}\right)^{2}
$$

## PowerMaker2&#x20;

Capped Power-4 Invariant tracks a quartic payoff to the borrower of the LP share.

$$
\varphi(R_{1},R_{2}) = R_{1} + p_{0}^{4} - (p_1^{3}+\frac{-3}{4}R_{2})^{\frac{4}{3}}
$$

$$
R_{1} - (p_1^{3}-\frac{3}{4}R_{2})^{\frac{4}{3}}
$$

