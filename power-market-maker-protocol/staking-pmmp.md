# Liquid Staking Boost

Liquid staking boost is a special application of PMMP. For the concept of what it does please see [here](../concepts/liquid-staking-boost.md).

## stPMMP

[Source code](https://github.com/Numoen/stpmmp)

staking PMMP is a special application of PMMP specifically for liquid staking that requires some static parameters to be changed. Interest rate parameters have been updated for the fact that liquid staking derivatives and their underlying native tokens have much lower volatility than they would in other cases.&#x20;

### Changelog

Three constants (`kink`, `multiplier`, and `jumpMultiplier`) have been changed in `JumpRate.sol` which therefore caused the `Lendgine.sol` creation code hash to be different. Other than that the codebases are identical. No audit has been performed on stPMMP.

### stPMMP deployment address

| Contract                                                | Arbitrum, Polygon Address                                                                                           |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| [Factory](smart-contracts/factory.md)                   | <pre class="language-solidity"><code class="lang-solidity">0x58db4e36755699188ff21E68A11308fDEb8792b5
</code></pre> |
| [LiquidityManager](smart-contracts/liquiditymanager.md) | <pre class="language-solidity"><code class="lang-solidity">0xe964F66B143E2C4752F3F4d37bfc9e74dE4e6eEB
</code></pre> |
| [LendgineRouter](smart-contracts/lendginerouter.md)     | <pre class="language-solidity"><code class="lang-solidity">0xC63292042D983C2196ab52F4101043F128EcEF67
</code></pre> |
