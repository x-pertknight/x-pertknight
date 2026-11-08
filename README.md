# Marco Amendola

On-chain risk research on prediction markets and DeFi. Every study here ships with its data, its code, and a command that reproduces the published numbers. Predictions are written before the run, failed ones stay in the log, and wrong claims are retracted in public.

Dune: [xpertknight](https://dune.com/xpertknight) · LinkedIn: [marco-bc-amendola](https://www.linkedin.com/in/marco-bc-amendola) · Barcelona

## Prediction market integrity

| Study | What it shows | Data and code |
|---|---|---|
| CFTC v. Van Dyke, reconciled to the chain | Every trading figure in the first prediction market insider trading case ties to the wallet's USDC.e receipts on Polygon to the cent. Also documents how naive fill parsing inflates a wallet's buys by 49 percent. | [repo](https://github.com/x-pertknight/polymarket-vandyke-receipts) · `python3 -I code/recompute.py` |
| The Missing Greek: settlement risk on Polymarket and UMA | 14.0 percent of 973 disputed resolutions changed outcome. The settlement premium is 8.5 to 21 bps depending on regime. Positioned DVM voters do vote their own book (63.2 percent) but changed 0 of 939 outcomes. | [repo](https://github.com/x-pertknight/traptrade) · [post](https://www.linkedin.com/posts/marco-bc-amendola_defi-predictionmarkets-riskmanagement-share-7484989110667935745-znxB) |
| UMA oracle base rates | 1.17M assertions, 0.31 percent disputed, 31 percent of disputes overturned. | [Dune](https://dune.com/xpertknight/uma-oracle-base-rates-vs-anecdotes) · [live](https://dune.com/xpertknight/uma-oracle-resolution-risk-live-base-rates) · [size](https://dune.com/xpertknight/does-optimistic-oracle-risk-scale-with-size-polymarket-uma) |
| Insider trading screening heuristics | Explainable rules for screening trading around event-driven markets from public data. One worked example. Outputs are leads, not accusations. | [repo](https://github.com/x-pertknight/polymarket-insider-detection) |

## DeFi risk

| Study | What it shows | Data and code |
|---|---|---|
| Uniswap v3 rebalancing | At a 5 percent width, re-centering needs a 111.6 percent fee APR to break even on a trending window. Mostly not worth it. | [repo](https://github.com/x-pertknight/clre-rebalancing-study) · `python3 reproduce_gate.py` · [monitor](https://dune.com/x1a0x1a0/clre-break-even-monitor) |
| Liquity V2: who sets the interest rate | Batch managers set the rate on 58.7 percent of live debt, and upfront fees from rate changes fall on the delegator. | [Dune](https://dune.com/x1a0x1a0/liquity-v2-who-actually-sets-the-interest-rate) |
| Crypto card mirage | About 8 percent of claimed neobank card volume is verifiable on-chain. | [Dune](https://dune.com/xpertknight/the-crypto-card-mirage) |
| Synthetic dollar yield stack | Ethena, Pendle and Morpho carry, tracked live. | [stack](https://dune.com/xpertknight/the-synthetic-dollar-yield-stack-ethena-pendle-morpho) · [carry](https://dune.com/xpertknight/the-synthetic-dollar-carry-trade-live-on-chain-susde-ethena) |
| Morpho curated lending | Risk and concentration across curated vaults. | [Dune](https://dune.com/xpertknight/morpho-curated-lending-risk-concentration) |
| Pegs are binary | Stablecoin pegs tracked as a binary state, at peg or broken. | [Dune](https://dune.com/xpertknight/pegs-are-binary-at-peg-or-dead) |
| App revenue concentration | As of July 2026, two apps collected 67 percent of crypto app-layer revenue. Tracked live. | [Dune](https://dune.com/x1a0x1a0/crypto-app-revenue-concentration) |

## Method

1. Read the docs, audits and governance first. State what is documented and what still has to be measured.
2. Write the prediction before running anything.
3. Rebuild from public data, keep the raw inputs, and make the result reproducible offline.
4. Run an adversarial review before publishing. Retractions stay visible.

Not investment advice. Findings about wallets are reported in aggregate unless a wallet is named in public charging documents.
