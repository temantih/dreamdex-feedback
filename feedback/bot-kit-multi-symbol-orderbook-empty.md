# Official bot-kit breaks multi-symbol orderbook requests

Severity: normal

Area: SDK

## Steps to reproduce

1. Open the official bot-kit file `rest.ts` and read line 72: the
   `/orderbooks` request is built with `symbols.join(",")`.
2. Read the API documentation for `/orderbooks`: it warns that this
   exact pattern produces `[]` silently.
3. Issue a multi-symbol orderbook request through the kit.

## Expected

A multi-symbol orderbook request returns the orderbooks for the requested
symbols.

## Actual

The response is an empty array, with no error. Single-symbol requests
work; only the multi-symbol path built by the kit is broken. This is a
direct code-versus-documentation deviation: the kit does the thing its own
docs warn against.

## Evidence

Bot-kit source (`rest.ts`, line 72), the `/orderbooks` documentation
warning, and the empty-array response to a multi-symbol request through
the kit.

## Environment

SDK version: not recorded in the original report
Network: Somnia Tokyo testnet
Wallet address: 0xA3172a1ff52524803A2232BB9AB4d68F180EBbC6
Date tested: October 2026
