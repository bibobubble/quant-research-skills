# Alpha And Backtesting

Use this reference for signal research, factor testing, backtest review, and judging skill versus luck.

## Define Alpha Carefully

Alpha means expected excess return after accounting for the relevant benchmark, risk factors, costs, and implementation constraints. A signal that earns returns through market beta, sector exposure, size, value, momentum, carry, liquidity, or volatility exposure is not necessarily useless, but it must be labeled correctly.

## Pre-Portfolio Signal Tests

Prefer simple, transparent tests before optimization:

- Coverage: number of assets with valid signal by date.
- Distribution: outliers, discreteness, missing values, stale values.
- Turnover: rank turnover and expected holding period.
- Decay: forward return relationship at multiple horizons.
- Rank IC: Spearman correlation between signal and future returns.
- Spread portfolio: long top bucket, short bottom bucket, with realistic delay.
- Monotonicity: bucket returns should broadly improve with signal rank.
- Neutralized signal behavior: test after removing market, sector, country, size, or style exposures.
- Stability: examine subperiods, regions, sectors, volatility regimes, and liquidity buckets.

## Backtesting Protocol

Use time-respecting validation. Do not randomly split time series unless the task is explicitly cross-sectional and leakage is controlled.

Typical protocol:

1. Freeze data definitions and timestamp rules.
2. Split into research, validation, and final holdout periods.
3. Fit transformations only on past data.
4. Use walk-forward evaluation for changing parameters.
5. Include rebalance timing, execution delay, unavailable data, borrow limits, corporate action handling, and delisting returns.
6. Deduct transaction costs and market impact before judging viability.
7. Keep a record of tried variants to account for multiple testing.

## Data Snooping Checks

Be skeptical when:

- Many signals were tried but only the winner is reported.
- Performance disappears after neutralization.
- Results depend on a narrow date range or one crisis period.
- Performance is concentrated in illiquid names.
- Gross returns are good but net returns collapse after costs.
- A signal has very high turnover relative to expected edge.
- The same data is used for feature selection, parameter fitting, and final evaluation.

## Metrics To Report

Report both signal-level and portfolio-level metrics:

- Mean return, volatility, Sharpe, hit rate, skew, drawdown.
- Rank IC mean, IC volatility, IC t-stat, IC decay.
- Long-short spread returns and bucket monotonicity.
- Turnover, capacity, cost drag, and borrow drag.
- Beta, sector, country, style, and liquidity exposures.
- Performance by subperiod and regime.

## Skill Versus Luck

Treat high Sharpe as a hypothesis, not proof. Ask:

- How many variants were searched?
- Is the result robust to reasonable implementation changes?
- Does the signal have an economic rationale?
- Does it survive neutralization and realistic costs?
- Is performance distributed across many bets or concentrated in a few names/dates?
- Are errors correlated across assets or time, reducing effective sample size?

## Recommended Response Shape

When reviewing a backtest:

1. Summarize what the backtest claims.
2. Identify the key leakage and overfitting risks.
3. Separate gross alpha evidence from net implementable evidence.
4. Recommend the next validation experiments.
5. State whether the signal is research-worthy, inconclusive, or likely invalid.
