# The Funding page does not disclose the funding rate formula, cap, or interest component

Severity: normal

Area: docs

## Steps to reproduce

1. Read the Funding documentation page and note what is missing: no
   funding rate formula, no cap, no interest component.
2. Read the official bot-kit: it records the rate as "pinned at the
   positive interest floor" in most markets.
3. Compute the structural cost at a 1 bp per 8-hour floor: 0.01% * 3
   periods per day * 365 days = ~10.95% APR paid by longs.

## Expected

The Funding page discloses the funding rate formula, its cap, and its
interest component, including the effective cost to traders.

## Actual

The Funding page discloses none of this, so a trader holding a long
position cannot see a ~10.95% APR structural cost from the official
documentation. The cost is not a bug in the funding mechanism itself; it
is a disclosure gap.

## Evidence

The Funding documentation page (formula, cap, and interest component all
absent) and the bot-kit note that the rate is "pinned at the positive
interest floor" in most markets, with the APR computed above.

## Environment

SDK version: not recorded in the original report
Network: Somnia Tokyo testnet (Hideki chain 50383)
Wallet address: (to be added by submitter)
Date tested: October 2026
