# Core Framework

Use this reference when the user asks for a broad quant investment analysis, research plan, or explanation of how the pieces fit together.

## Main Map

Quantitative investing connects five components:

1. Return model: estimate expected excess returns or alpha.
2. Risk model: estimate volatility, covariance, factor exposures, and idiosyncratic risk.
3. Portfolio model: transform forecasts into positions subject to objectives and constraints.
4. Trading model: account for turnover, transaction costs, market impact, capacity, and execution schedule.
5. Attribution model: explain realized PnL and feed lessons back into research.

Do not analyze these components in isolation. A strong alpha can be unusable after risk, cost, or capacity constraints. A good risk model can still produce bad portfolios if estimation error is amplified by optimization.

## Questions To Ask First

- What is the universe: equities, futures, FX, options, credit, crypto, or multi-asset?
- What is the horizon: intraday, daily, weekly, monthly, or strategic?
- What is the rebalance frequency and expected holding period?
- What is the objective: absolute return, benchmark-relative return, risk parity, hedging, liquidation, or capacity-aware scaling?
- What constraints bind: leverage, net/gross exposure, beta, sectors, countries, turnover, borrow, liquidity, concentration, drawdown?
- What are the forecasts: expected excess returns, covariance, cost, borrow, and corporate action handling?
- What data is available and timestamped correctly?

## Analysis Sequence

1. Define excess returns relative to cash, benchmark, or tradable hedge.
2. Establish a clean returns construction process: prices, dividends, splits, corporate actions, survivorship, delistings, FX conversion, and timestamp alignment.
3. Build the alpha signal and define its expected holding horizon.
4. Run pre-portfolio tests: rank IC, spread returns, monotonicity, turnover, decay, coverage, missingness, crowding, and regime behavior.
5. Build the risk model: factor exposures, factor covariance, idiosyncratic variance, and shrinkage.
6. Construct a portfolio with realistic constraints and cost model.
7. Run out-of-sample and walk-forward performance with costs.
8. Attribute realized and simulated PnL.
9. Diagnose whether performance comes from alpha, risk premia, leverage, timing, sector/country bets, data leakage, or chance.

## Common Failure Modes

- Optimizing noisy alphas too aggressively.
- Treating portfolio backtest returns as independent observations.
- Ignoring turnover and market impact.
- Using cross-sectional information that would not have been known at trade time.
- Letting constraints hide risk exposure instead of measuring it.
- Confusing factor exposure with alpha.
- Reporting Sharpe without capacity, drawdown, skew, turnover, and live decay.

## Good Deliverables

A useful quant analysis should usually include:

- Research question and portfolio objective.
- Data construction notes.
- Validation design.
- Alpha evidence before and after risk neutralization.
- Risk model summary and diagnostics.
- Portfolio construction setup.
- Cost and capacity assumptions.
- Performance decomposition.
- Limitations and next experiments.
