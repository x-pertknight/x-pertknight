# Numbers

Every headline figure on this profile, with what it counts. Each one was checked against the data or script output of its repo on the date in the last column.

## Headline figures

| Figure | What it measures | Scope | Window | Unit | Repo | Source | Checked |
|---|---|---|---|---|---|---|---|
| 0 debt, all five PegKeepers | crvUSD debt held by each PegKeeper at the start and end of the window | USDC, USDT, pyUSD, frxUSD, GHO PegKeepers | 2026-11-08 20:00 to 2026-11-09 04:00 UTC | crvUSD | crvusd-soft-liquidation-flush | `data/pegkeeper_debt.csv`; `python3 -I code/recompute.py` | 2026-11-22 |
| 23:49:35 UTC on 29 October 2026, block 26,301,792 | Last Withdraw by the USDT PegKeeper, after which its debt was under 1 crvUSD; the other four already held none | USDT PegKeeper | hourly samples from 2026-08-31 23:16 UTC to block 26,430,593 (2026-11-16 22:30:47 UTC) | event | crvusd-soft-liquidation-flush | `data/r2_events.csv` line 291; README line 25; RELEASE2.md lines 5 and 10 | 2026-11-22 |
| 3.85M | Net crvUSD sold into the peg pools by transactions that went through Curve pools where Yield Basis is the LP (main measure V0) | Five PegKeeper pools | 2026-11-08 20:00 to 2026-11-09 04:00 UTC | crvUSD | crvusd-soft-liquidation-flush | `data/results.json` `V0_main_net_same_tx` = 3,854,933; README line 30 | 2026-11-22 |
| 0.9979 to 0.9942 | TVL weighted crvUSD price across the five PegKeeper pools at the window start and at its low (21:56:35 UTC) | Five PegKeeper pools | same | price | crvusd-soft-liquidation-flush | `data/results.json` `W_pre` = 0.99795, `q1.W.min` = 0.99425; README lines 15 and 17 | 2026-11-22 |
| 0.49 | Median ratio of crvUSD sold into the peg pools to the USD value of BTC or ETH sold into the volatile crvUSD pools | Ten BTC or ETH drawdowns (22 qualified, capped at 10) | 2025-09-24 (first Yield Basis market) to 2026-11-09 | ratio | crvusd-soft-liquidation-flush | README lines 104, 106 and 121 | 2026-11-22 |
| 1.43M | UMA questions with a proposal | Polymarket's three UMA paths | 11 October to 17 November 2026 | question | settlement-tracker | RESULTS.md line 33 (1,434,227); not recomputable from published data | 2026-11-22 |
| 1,037 (0.07%) | Questions disputed, as a share of questions proposed | same | same | question | settlement-tracker | RESULTS.md line 34; `data/disputes_final.json` (1,037 rows); the 0.07% is not recomputable from published data | 2026-11-22 |
| 223 of 929 (24.0%) | Disputed markets settled by the cutoff whose final outcome differs from the first proposal | same | same | market | settlement-tracker | RESULTS.md line 37; `data/disputes_final.json` | 2026-11-22 |
| 16.6% to 35.0% | 95% interval for the 24.0%, resampling whole hours of disputes (199 hours) | same | same | market | settlement-tracker | RESULTS.md line 61 | 2026-11-22 |
| 169 of 243 (70%) | Among settled disputed markets where the vote ruled on the facts, the share whose final outcome differs from the first proposal | same | same | market | settlement-tracker | RESULTS.md lines 54 and 59; not recomputable from published data | 2026-11-22 |
| 49 percent | Buys a parser would add by booking taker field rows to the wallet (16,699.75 USDC.e), as a share of the wallet's real buys (33,934.34 USDC.e) | The wallet named in CFTC v. Van Dyke | the wallet's 15 trade transactions | USDC.e | polymarket-vandyke-receipts | `python3 -I code/recompute.py`; NOTE-orderfilled-attribution.md line 32 | 2026-11-22 |
| 4,423 | Settled disputed price requests | OptimisticOracleV2 and ManagedOptimisticOracleV2 on Polygon, every requester | 365 days to 2026-11-17 10:37 UTC | price request | uma-disputes-live | README line 32; `data/outcome_shares_by_month.csv` row "12 months" | 2026-11-22 |
| 54.2% / 22.2% / 23.6% | Reset as too early / overturned on the facts / upheld, as shares of all settled disputes (2,397 / 981 / 1,045) | same | same | price request | uma-disputes-live | same row | 2026-11-22 |
| 48.4% | Overturned of decided: overturned divided by overturned plus upheld, resets left out | same | same | price request | uma-disputes-live | same row | 2026-11-22 |
| 136 of 973 (14.0%) | Disputes whose final outcome differs from the original proposal: 67 direct flips plus 69 flips after a too early reset. One ambiguous case with a 0.5 proposal is left out; counting it gives 137 | Polymarket's classic UMA adapters, disputes that reached the DVM | 1 April 2025 to 1 July 2026 | disputed question | prediction-market-integrity | `python3 -I scripts/reproduce.py` (needs the packages in requirements.txt), section 1, HEADLINE | 2026-11-22 |
| 74.7% (retracted) | Disputes where the DVM did not confirm the proposal (727 of 973), 656 of them too early resets | same | same | disputed question | prediction-market-integrity | `python3 -I scripts/reproduce.py` (needs the packages in requirements.txt), section 1 | 2026-11-22 |
| 111.6% | Fee APR needed to break even when recentering a ±5% range on exit | Simulation on Coinbase ETH/USD hourly prices, trending window A | 2026-04-09 to 2026-07-08 | annual fee rate | clre-rebalancing-study | `runs/run002.json` `A.rows[4].be` = 1.11575; `python3 reproduce_gate.py` | 2026-11-22 |

## Not verifiable

| Figure | What it was | Why it is not used |
|---|---|---|
| 31% | Overturns among UMA disputes decided on substance, too early resets left out, from the Dune dashboard UMA Oracle, Base Rates vs Anecdotes | When checked on 18 November 2026 the dashboard's stored results had expired, so the figure could not be confirmed. It is not a finding and is not quoted on this profile. |

## Why 14%, 24%, 31%, 48% and 70% are different numbers

They all describe UMA disputes, but they answer different questions.

* **14.0%** follows each dispute on Polymarket's classic adapters to the final outcome of the question, including questions that were reset as too early and proposed again. Window April 2025 to July 2026.
* **24.0%** asks the same question (final outcome against the first proposal) on a later window that does not overlap, 11 October to 17 November 2026. 1,019 of its 1,037 disputes are on the two paths that use the newer managed oracle. It counts markets and leaves out the 108 still open at the cutoff.
* **70%** is the rate among settled markets where the vote ruled on the facts (169 of 243). Most disputes (660 of 1,037) were voted too early, and in those the first answer nearly always stood. The 24.0% is the mix of the two.
* **48.4%** stops at what the vote said about one price request: overturned divided by overturned plus upheld, resets left out, for every requester on two Polygon oracles over 12 months. A reset that later settles on the first answer is not counted as unchanged; it is left out.
* **31%** came from a dashboard query over the lifetime of three oracle versions on Polygon, every requester, per request. It used the same kind of ratio as the 48.4% on a much wider scope. It could not be checked (see above).

The settlement-tracker README, lines 47 to 55, gives the same reconciliation from that repo's side.
