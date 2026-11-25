# Numbers

Every headline figure on this profile, with what it counts. Each one was checked against the data or script output of its repo on the date in the last column.

## Headline figures

| Figure | What it measures | Scope | Window | Unit | Repo | Source | Checked |
|---|---|---|---|---|---|---|---|
| 0 debt, all five PegKeepers | crvUSD debt held by each PegKeeper at the start and end of the window | USDC, USDT, pyUSD, frxUSD, GHO PegKeepers | 2026-11-08 20:00 to 2026-11-09 04:00 UTC | crvUSD | crvusd-soft-liquidation-flush | `data/pegkeeper_debt.csv`; `python3 -I code/recompute.py` | 2026-11-22 |
| 3.85M | Net crvUSD sold into the peg pools by transactions that went through Curve pools where Yield Basis is the LP (main measure V0) | Five PegKeeper pools | 2026-11-08 20:00 to 2026-11-09 04:00 UTC | crvUSD | crvusd-soft-liquidation-flush | `data/results.json` `V0_main_net_same_tx` = 3,854,933; README line 32 | 2026-11-22 |
| 0.9979 to 0.9942 | TVL weighted crvUSD price across the five PegKeeper pools at the window start and at its low (21:56:35 UTC) | Five PegKeeper pools | same | price | crvusd-soft-liquidation-flush | `data/results.json` `W_pre` = 0.99795, `q1.W.min` = 0.99425; README lines 17 and 19 | 2026-11-22 |
| 40% and 33% | sUSDe withdrawn from the market that the receiving address matched with an Ethena unstake started within three days, by two counting rules (cap per address over its life, cap per address per withdrawal day) | sUSDe / PYUSD market on Morpho, Ethereum; 392 million sUSDe withdrawn | January to 23 November 2026 | share of sUSDe, matched by address | susde-loop-exit-cost | `data/results.json` `exit_paths`; `python3 code/analyze.py` | 2026-11-25 |
| 5.7% and 5.2% | sUSDe sold by the receiving address on a DEX or through CoW Protocol within three days of a withdrawal, by the same two rules | same | same | share of sUSDe, matched by address | susde-loop-exit-cost | `data/results.json` `receivers_sales` | 2026-11-25 |
| 1,037 | Questions disputed | Polymarket's three UMA paths | 11 October to 17 November 2026 | question | settlement-tracker | RESULTS.md line 34; `data/disputes_final.json` (1,037 rows) | 2026-11-22 |
| 223 of 929 (24.0%) | Disputed markets settled by the cutoff whose final outcome differs from the first proposal | same | same | market | settlement-tracker | RESULTS.md lines 35 and 37; `data/disputes_final.json` | 2026-11-22 |
| 16.6% to 35.0% | 95% interval for the 24.0%, resampling whole hours of disputes (199 hours) | same | same | market | settlement-tracker | RESULTS.md line 61 | 2026-11-22 |
| 49 percent | Buys a parser would add by booking taker field rows to the wallet (16,699.75 USDC.e), as a share of the wallet's real buys (33,934.34 USDC.e) | The wallet named in CFTC v. Van Dyke | the wallet's 15 trade transactions | USDC.e | polymarket-vandyke-receipts | `python3 -I code/recompute.py`; NOTE-orderfilled-attribution.md line 32 | 2026-11-22 |
| 4,423 | Settled disputed price requests | OptimisticOracleV2 and ManagedOptimisticOracleV2 on Polygon, every requester | 365 days to 2026-11-17 10:37 UTC | price request | uma-disputes-live | README line 34; `data/outcome_shares_by_month.csv` row "12 months" | 2026-11-22 |
| 54.2% / 22.2% / 23.6% | Reset as too early / overturned on the facts / upheld, as shares of all settled disputes (2,397 / 981 / 1,045) | same | same | price request | uma-disputes-live | same row | 2026-11-22 |
| 136 of 973 (14.0%) | Disputes whose final outcome differs from the original proposal: 67 direct flips plus 69 flips after a too early reset. One ambiguous case with a 0.5 proposal is left out; counting it gives 137 | Polymarket's classic UMA adapters, disputes that reached the DVM | 1 April 2025 to 1 July 2026 | disputed question | prediction-market-integrity | `python3 -I scripts/reproduce.py` (needs the packages in requirements.txt), section 1, HEADLINE | 2026-11-22 |
| 74.7% (retracted) | Disputes where the DVM did not confirm the proposal (727 of 973), 656 of them too early resets | same | same | disputed question | prediction-market-integrity | `python3 -I scripts/reproduce.py` (needs the packages in requirements.txt), section 1 | 2026-11-22 |
| 111.6% | Fee APR needed to break even when recentering a ±5% range on exit | Simulation on Coinbase ETH/USD hourly prices, trending window A | 2026-04-09 to 2026-07-08 | annual fee rate | clre-rebalancing-study | `runs/run002.json` `A.rows[4].be` = 1.11575; `python3 reproduce_gate.py` | 2026-11-22 |
| 1.678 | Median ratio of cash counted by crediting every fill to both its maker and its taker, to the collateral that crossed trader wallets in the receipts | 60 Polymarket markets (30 standard, 30 neg-risk) | markets that closed in October 2026 | ratio | polymarket-fill-counting | README line 17; `python3 -I code/compute.py all` (`data/results_all.json`) | 2026-11-23 |
| 21 of 35 | Markets where Polymarket's reported volume (Gamma `volumeNum`) is within 5% of the sum of all fill rows | the 35 of those 60 markets read in full | same | market | polymarket-fill-counting | README line 31 | 2026-11-23 |

## Why 14% and 24% are different numbers

Both describe UMA disputes, but they answer different questions.

* **14.0%** follows each dispute on Polymarket's classic adapters to the final outcome of the question, including questions that were reset as too early and proposed again. Window April 2025 to July 2026.
* **24.0%** asks the same question (final outcome against the first proposal) on a later window that does not overlap, 11 October to 17 November 2026. 1,019 of its 1,037 disputes are on the two paths that use the newer managed oracle. It counts markets and leaves out the 108 still open at the cutoff.

The settlement-tracker README, lines 47 to 55, gives the same reconciliation from that repo's side.

## Published earlier, since superseded

| Figure | What it was | Why it is not used |
|---|---|---|
| 31% | Overturns among UMA disputes decided on substance, too early resets left out, from my Dune dashboard UMA Oracle, Base Rates vs Anecdotes | A rerun on 22 November 2026 gives 42.6% over the oracle's lifetime to that date (1,140 of 2,673 disputes decided on substance); 31% was the reading of 2 July 2026. The rate has risen since, so neither figure is quoted in this README. The dashboard's own text states the 42.6% with its date. |

It differs from the 14% and the 24% because it came from a dashboard query over the lifetime of three oracle versions on Polygon, every requester, counted per request, a much wider scope than either study.
