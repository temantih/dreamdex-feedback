# Documentation says the testnet builder-fee cap is 0 / disabled, live value is 100000

Severity: normal

Area: docs

## Steps to reproduce

1. Read the `getMaxBuilderFeeBpsTimes1k()` reference page (around line
   1573) and the Stop Orders page: both claim the testnet builder-fee
   cap is `0` / "disabled at v1.0".
2. Call the getter with `eth_call` on five sample pools (mainnet and
   Shannon pools).

## Expected

The testnet builder-fee cap is `0` / disabled, as the documentation
claims.

## Actual

Every call returns `100000`. The documentation's main claim (100000 for
all pools) is correct for spot; only the testnet-specific claim of
0/disabled is wrong.

## Evidence

`eth_call` results on five sample pools across mainnet and Shannon, all
returning `100000`, against the two documentation pages quoted above.

## Environment

SDK version: not recorded in the original report
Network: Somnia Tokyo testnet
Wallet address: (to be added by submitter)
Date tested: October 2026
