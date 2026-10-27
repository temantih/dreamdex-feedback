# The perps builder-fee cap (10000) appears nowhere in the documentation

Severity: normal

Area: docs

## Steps to reproduce

1. Call the builder-fee getter with `eth_call` on three sample perps pools
   on Hideki.
2. Search the official documentation for the perps builder-fee cap and
   for builder fees in the perps fee tables.

## Expected

The perps builder-fee cap is documented, alongside the spot value.

## Actual

All three perps pools return `10000` (10 bps). No documentation page
states this value, and the perps fee tables do not list builder fees at
all, so a perps builder has no official source for the fee cap that
actually applies to them.

## Evidence

`eth_call` results on three sample perps pools on Hideki, all returning
`10000`, plus the absence of the value from the documentation and fee
tables searched.

## Environment

SDK version: not recorded in the original report
Network: Somnia Tokyo testnet (Hideki chain 50383)
Wallet address: 0xA3172a1ff52524803A2232BB9AB4d68F180EBbC6
Date tested: October 2026
