# Marco Amendola

On-chain risk research on prediction markets and DeFi. Every study here ships with its data, its code, and a command that reproduces the published numbers. Predictions are written before the run, failed ones stay in the log, and wrong claims are retracted in public.

Dune: [xpertknight](https://dune.com/xpertknight), [x1a0x1a0](https://dune.com/x1a0x1a0) · LinkedIn: [marco-bc-amendola](https://www.linkedin.com/in/marco-bc-amendola) · Barcelona

## Prediction market integrity

| Study | What it shows | Data and code |
|---|---|---|
| CFTC v. Van Dyke, checked against the chain | The trading figures alleged in the first CFTC insider trading case involving event contracts (trial pending), reproduced from the wallet's Polygon receipts within the documents' rounding. Also shows that crediting taker-field fill rows to the wallet would overstate its buys by 49 percent. | [repo](https://github.com/x-pertknight/polymarket-vandyke-receipts) · [charts](https://x-pertknight.github.io/polymarket-vandyke-receipts/) · `python3 -I code/recompute.py` |
| The Missing Greek: settlement risk on Polymarket and UMA | On the classic resolution path, 136 of 973 disputed resolutions (14.0 percent) changed outcome. The settlement premium is 8.5 to 21 bps depending on regime. Positioned DVM voters do vote their own book (63.2 percent) but changed 0 of 939 outcomes. | [repo](https://github.com/x-pertknight/prediction-market-integrity) · [post](https://www.linkedin.com/posts/marco-bc-amendola_defi-predictionmarkets-riskmanagement-share-7484989110667935745-znxB) |
| UMA oracle base rates | 1.17M assertions on Polygon, 0.31 percent disputed. Of disputes decided on substance, with too-early resets excluded, 31 percent overturned the proposer. | [Dune](https://dune.com/xpertknight/uma-oracle-base-rates-vs-anecdotes) · [live](https://dune.com/xpertknight/uma-oracle-resolution-risk-live-base-rates) · [size](https://dune.com/xpertknight/does-optimistic-oracle-risk-scale-with-size-polymarket-uma) |

## DeFi risk

| Study | What it shows | Data and code |
|---|---|---|
| crvUSD in the 8 November 2026 ETH flush | All five PegKeepers held zero debt. A net 3.85M crvUSD was sold into the peg pools through Curve crvUSD pools where Yield Basis is the LP, 3.64M of it through the BTC pools, and the peg fell from 0.9979 to 0.9942. Across ten drawdowns since Yield Basis launched, the median ratio of crvUSD sold into the peg pools to BTC or ETH sold into the volatile crvUSD pools was 0.49. | [repo](https://github.com/x-pertknight/crvusd-soft-liquidation-flush) · `python3 -I code/recompute.py` |
| Uniswap v3 rebalancing | At a 5 percent width, re-centering needs a 111.6 percent fee APR to break even on a trending window. Mostly not worth it. | [repo](https://github.com/x-pertknight/clre-rebalancing-study) · `python3 reproduce_gate.py` · [monitor](https://dune.com/x1a0x1a0/clre-break-even-monitor) |
| Liquity V2: who sets the interest rate | As of 26 July 2026, batch managers set the rate on 58.7 percent of live debt, and upfront fees from rate changes fall on the delegator. | [Dune](https://dune.com/x1a0x1a0/liquity-v2-who-actually-sets-the-interest-rate) |
| Crypto card mirage | About 8 percent of claimed neobank card volume ($726M of a claimed $9B) was verifiable on-chain at publication. | [Dune](https://dune.com/xpertknight/the-crypto-card-mirage) |
| Synthetic dollar yield stack | Ethena, Pendle and Morpho carry, tracked live. | [stack](https://dune.com/xpertknight/the-synthetic-dollar-yield-stack-ethena-pendle-morpho) · [carry](https://dune.com/xpertknight/the-synthetic-dollar-carry-trade-live-on-chain-susde-ethena) |
| Morpho curated lending | Risk and concentration across curated vaults. | [Dune](https://dune.com/xpertknight/morpho-curated-lending-risk-concentration) |
| Pegs are binary | Stablecoin pegs tracked as a binary state, at peg or broken. | [Dune](https://dune.com/xpertknight/pegs-are-binary-at-peg-or-dead) |
| App revenue concentration | Revenue share among Hyperliquid, Pump.fun and Ethena. The 67 percent figure for the top two is from the July 2026 article, on Token Terminal data. | [Dune](https://dune.com/x1a0x1a0/crypto-app-revenue-concentration) |

## Method

1. Read the docs, audits and governance first. State what is documented and what still has to be measured.
2. Write the prediction before running anything.
3. Rebuild from public data, keep the raw inputs, and make the result reproducible offline.
4. Run an adversarial review before publishing. Retractions stay visible.

Not investment advice. Findings about wallets are reported in aggregate unless the wallet is the subject of public charging documents. Dune links show the SQL and method; some charts stay empty until the queries are rerun.
