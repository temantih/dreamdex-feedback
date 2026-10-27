# Two testnets, one address set, no page explaining the difference

Severity: normal

Area: docs

## Steps to reproduce

1. Read the perps developer documentation: it states the perps testnet
   is Hideki, chain 50383.
2. Read the contract-addresses page: it labels the same addresses as
   Shannon, chain 50312.
3. Search the documentation for any page explaining two testnets or
   shared singleton addresses.

## Expected

Contract addresses are labeled with the correct chain, and the
documentation explains the testnet setup.

## Actual

Both pages exist and contradict each other, and no page resolves the
contradiction. Connecting to Shannon with perps addresses shows empty
state at apparently correct addresses, so an integrator following one
page connects to the wrong chain and wastes hours debugging a labeling
problem.

## Evidence

The perps developer documentation (Hideki, chain 50383) and the
contract-addresses page (Shannon, chain 50312) labeling the same
addresses, with no page explaining two testnets or shared singleton
addresses.

## Environment

SDK version: not recorded in the original report
Network: Somnia Tokyo testnet (Hideki 50383 / Shannon 50312)
Wallet address: 0xA3172a1ff52524803A2232BB9AB4d68F180EBbC6
Date tested: October 2026
