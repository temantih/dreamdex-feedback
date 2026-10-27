# Documentation bundle: CCXT symbol, perps reference, leverage, vouchers, liquidation stages, auth ordering

Severity: normal

Area: docs

## Steps to reproduce

1. Open the CCXT examples and search for `SOMI/USDC`: it appears in
   more than ten examples, but the symbol does not exist.
2. Open the Contracts reference: it covers spot contracts only, with no
   perps function, event, or error specifications.
3. Compare the leverage documentation (extra margin per position) with
   the bot-kit behavior (extra margin against the whole account).
4. Read the voucher documentation: two mechanism versions are described
   and no activation path is documented for isolated accounts.
5. Compare the roadmap's six-stage liquidation waterfall with the
   trading documentation's five stages.
6. Call `GET /v0/portfolio` with no authentication and observe the
   response code.

## Expected

The documentation is consistent: examples use real symbols, the perps
contracts are specified, leverage semantics match the kit, the voucher
activation path is documented, the liquidation stage count agrees across
pages, and the portfolio endpoint returns 401 without authentication.

## Actual

- **CCXT example uses a nonexistent symbol.** More than ten CCXT
  examples use `SOMI/USDC`, a symbol that does not exist.
- **No perps contract reference.** The Contracts reference covers spot
  only.
- **Contradictory leverage semantics.** Docs say extra margin applies
  per position; the bot-kit applies it against the whole account.
- **Two voucher mechanisms, no activation path.** Two versions are
  described, and isolated accounts have no documented activation path.
- **Liquidation waterfall stage count.** The roadmap describes six
  stages; the trading documentation describes five.
- **Auth-before-validation ordering.** `GET /v0/portfolio` without
  authentication returns 400 rather than 401, showing validation runs
  before authentication. No data leak was observed from this.

## Evidence

The CCXT examples, the Contracts reference, the leverage documentation
versus bot-kit behavior, the voucher documentation, the roadmap versus
trading documentation, and the unauthenticated `GET /v0/portfolio`
response (400, not 401, no data leak observed).

## Environment

SDK version: not recorded in the original report
Network: Somnia Tokyo testnet (Hideki chain 50383)
Wallet address: (to be added by submitter)
Date tested: October 2026
