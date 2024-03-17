# Hedging Uniswap V3

PowerMaker enables anyone the ability to hedge impermanent loss on Uniswap. This is possible by minting a power perpetual through the PowerMaker AMM and matching the **positive gamma** with negative gamma of a Uniswap LP share.&#x20;

## Hedging Process <a href="#id-41d5" id="id-41d5"></a>

Hedging the impermanent loss of a Uniswap LP simply entails canceling out the negative gamma of a LP share with the positive gamma of a power perpetual.

For the example above we take a _ETH/USDC LP_ position with the following parameters:

```
ETH Price: $1825.53

USDC Price:$1

Lower Bound: $1600

Upper Bound: $2000
```

So to hedge the following Uniswap LP position we:

1. **Calculate the price of a Power Perpetual Token**

Becuase every Power Perpetual Token (PPT) is a **quadratic contract.** We know that it will square the price of an underlying asset, “squared leverage.” In fact, we also know that the **gamma will always be a constant 2** (this useful for the next step).

> The price of a PT = (Price of the underlying asset)².
>
> If ETH = $1825.53, then the price of a PT = (1825.53)² = 3332559.78

**2. Calculate the value of a Uniswap LP**

With Uniswap V3, the valuing a LP share get a bit more tricky as there is a lower bound and upper bound which refer to the prices between which the liquidity is concentrated on the AMM.

The value of a Uniswap LP is defined as:

<figure><img src="https://miro.medium.com/v2/resize:fit:967/0*uijeS5r7SseEo_5F" alt="" height="32" width="537"><figcaption></figcaption></figure>

<figure><img src="https://miro.medium.com/v2/resize:fit:922/0*DKKXC_E5UbeCLHss" alt="" height="29" width="512"><figcaption></figcaption></figure>

**3. Calculate the gamma of Uniswap LP**

Assuming that the price of the underlying asset is with in the lower and upper bound 0, then the gamma will be:

<figure><img src="https://miro.medium.com/v2/resize:fit:311/0*WVYosg0R2sPUEtfU" alt="" height="26" width="173"><figcaption></figcaption></figure>

If the price of ETH = $1825.53, then the gamma of the Uniswap LP is:

<figure><img src="https://miro.medium.com/v2/resize:fit:679/0*K04sDG6ZMsu2teYK" alt="" height="28" width="377"><figcaption></figcaption></figure>

**4. Calculate the number of Power Tokens.**

Using the positive gamma value and price of a Power Token we find the number of Power Tokens needed to hedge a Uniswap LP position.

<figure><img src="https://miro.medium.com/v2/resize:fit:160/0*WoI4edE97e2rmHlR" alt="" height="32" width="89"><figcaption></figcaption></figure>

Which is the gamma of Uniswap over the negative gamma of a Power Token. Therefore the number of PT needed is:

<figure><img src="https://miro.medium.com/v2/resize:fit:445/0*m2xBnXQ1hr0ZovdP" alt="" height="32" width="247"><figcaption></figcaption></figure>

## **Total Returns** <a href="#id-692d" id="id-692d"></a>

After analyzing the on-chain data for the 7 days `block.timestamp` we can chart the value of the hedged portfolio versus a non-hedge portfolio or “LP Value.” We show that the **hedge portfolio \[ETH/USDC LP] consistently outperforms across wide and tight bounds**.



<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

\
