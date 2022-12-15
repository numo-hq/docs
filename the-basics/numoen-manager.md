---
description: Numoen Manager facilitates using the Numoen Core protocol.
---

# Numoen Manager

## Ad

Numoen manager has basic features for safeguarding uses from stale transactions or slippage. Native tokens such as ETH are also wrapped.

When using leverage tokens, extra steps must be done so that all assets are in collateral and that the position value is equivalent to the specified value.

## Minting a leverage token

1. Use a flash loan to borrow speculative tokens
2. Use the flash loan + user funds to borrow LP tokens
3. Unwrap LP token and sell the underlying tokens into speculative tokens
4. Pay back the flash loan

## Burning a leverage token

1. Use a flash loan to borrow the underlying tokens of the Numoen LP
2. Mint the debt amount of LP tokens
3. Payback debt on Numoen
4. Reclaim the collateral of the position
5. Payback the flash loan and return extra collateral to the user

## Ad
