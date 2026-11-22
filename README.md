# Marco Amendola

DeFi risk analyst in Barcelona. I rebuild what happened on chain, check it against what the protocol docs and public filings say, and publish the data and code so the numbers can be rerun. Where a study wrote predictions down, the repo lists them and the ones that missed, and says what evidence there is for when they were written. Every repo states its limits.

## Start here

| Study | Finding | Rerun |
|---|---|---|
| [crvUSD in the 8 November 2026 ETH flush](https://github.com/x-pertknight/crvusd-soft-liquidation-flush) | All five PegKeepers held zero debt going in, so they had nothing to withdraw. A net 3.85M crvUSD was sold into the peg pools through Curve pools where Yield Basis is the LP, and the weighted peg fell from 0.9979 to 0.9942. Release 2 explains why the PegKeepers were empty. | `python3 -I code/recompute.py` |
| [Prediction market settlement tracker](https://github.com/x-pertknight/settlement-tracker) | On Polymarket's UMA paths, 1,037 questions proposed between 11 October and 17 November 2026 were disputed. 223 of the 929 that settled by the cutoff ended on a different outcome than first proposed (24.0%, 95% interval 16.6% to 35.0%). Admin override powers are documented from verified contract source; how often they are used is not measured. | `./reproduce.sh` |
| [CFTC v. Van Dyke, checked against the chain](https://github.com/x-pertknight/polymarket-vandyke-receipts) | The trading figures in the complaint and indictment reproduced, with USDC.e amounts from the wallet's Polygon receipts and share counts from Polymarket's public activity API. Two residuals are disclosed. Booking fills by the taker field would overstate the wallet's buys by 49 percent. | `python3 -I code/recompute.py` |

## Also

* [TBILL as collateral on Morpho](https://github.com/x-pertknight/tbill-collateral-memo): whether OpenEden's tokenized T-bill could back a Morpho market. Rejected today: transfers need issuer KYC approval, and neither Morpho Blue nor the busiest Morpho liquidators tested is approved.
* [UMA disputes on Polygon, 12 months](https://github.com/x-pertknight/uma-disputes-live): 4,423 settled disputes. 54% reset as too early, 22% overturned, 24% upheld. A dispute rate is not an error rate.
* [The Missing Greek](https://github.com/x-pertknight/prediction-market-integrity): settlement risk on Polymarket's classic UMA adapters, April 2025 to July 2026. In 136 of 973 disputes the final outcome differed from the original proposal (14.0%). An earlier headline of mine (74.7%) is retracted in the repo.
* [Uniswap v3 rebalancing](https://github.com/x-pertknight/clre-rebalancing-study): a simulation on hourly ETH/USD prices. Recentering a ±5% range needed a 111.6% fee APR to break even on a trending window.

Dispute figures differ across these studies because scope, window and unit differ. Each README says which. [numbers.md](numbers.md) lists every figure on this page with its scope, window, unit and source.

LinkedIn: [marco-bc-amendola](https://www.linkedin.com/in/marco-bc-amendola)

Not investment advice. Wallets are reported in aggregate. The one exception is a wallet identified in public charging documents.
