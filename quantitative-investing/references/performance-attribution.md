# Performance Attribution

Use this reference for ex post analysis, factor/idiosyncratic PnL, selection versus sizing, and explaining realized strategy returns.

## Purpose

Performance attribution should explain what happened, test whether the investment process behaved as intended, and feed improvements back into research and portfolio construction.

Do not stop at total return or Sharpe. Decompose realized PnL into the sources that were known or intended at portfolio construction time.

## Core Decompositions

Useful decompositions include:

- Factor PnL versus idiosyncratic PnL.
- Alpha PnL versus risk premia or benchmark exposure.
- Selection effect versus sizing effect.
- Timing effect versus static exposure.
- Gross PnL versus transaction cost, borrow, financing, and slippage.
- Forecast contribution versus optimization or constraint contribution.
- Planned exposure versus realized drift.

## Selection Versus Sizing

Selection asks whether the model ranked opportunities correctly. Sizing asks whether the portfolio allocated capital correctly across those opportunities.

A strategy can have:

- Good selection but poor sizing: signal ranks work, portfolio construction overweights bad risk/cost trades.
- Poor selection but good sizing: optimizer avoids damage, but alpha model lacks edge.
- Good gross selection but poor net result: costs or turnover overwhelm edge.

## Factor Attribution

For a factor model `r = X f + epsilon`, realized portfolio return can be decomposed into:

- Factor exposure times factor return.
- Idiosyncratic exposure times residual return.
- Costs and financing.

Use this to identify whether performance came from intended alpha or unintended market, sector, country, style, currency, liquidity, or volatility bets.

## Attribution With Error

Attribution depends on model quality. Treat unexplained residuals carefully:

- Factor definitions may be incomplete.
- Exposures may be noisy or stale.
- Covariance and beta estimates may drift.
- Trade timing may differ from accounting timing.
- Residuals can be correlated and clustered.

Report attribution uncertainty when estimates are noisy.

## Recommended Report

For a strategy or backtest, include:

1. Headline performance after costs.
2. Exposure summary: market, sector, country, style, currency, liquidity, and leverage.
3. PnL decomposition: factor, idiosyncratic, alpha, cost, and residual.
4. Selection versus sizing analysis.
5. Top contributors and detractors.
6. Regime or subperiod breakdown.
7. Explanation of whether results match the strategy's intended source of edge.
8. Research actions: improve signal, risk model, optimizer, cost model, or execution.

## Warning Signs

- Most PnL comes from unintended beta or sector exposure.
- Attribution flips sign under small model changes.
- Costs explain most drawdowns.
- A few names or dates explain most performance.
- Reported alpha disappears after benchmark or factor adjustment.
- The model cannot explain why the portfolio held its largest positions.
