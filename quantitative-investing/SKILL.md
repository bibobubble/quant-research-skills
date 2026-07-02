---
name: quantitative-investing
description: Quantitative investing research workflow inspired by Giuseppe A. Paleologo's The Elements of Quantitative Investing. Use when analyzing alpha signals, backtests, risk models, factor models, portfolio construction, transaction costs, hedging, Kelly sizing, drawdown control, capacity, or performance attribution for systematic trading and asset management.
---

# Quantitative Investing

## Core stance

Start from the investment decision, not from a model. Treat alpha research, risk modeling, portfolio construction, execution cost, and performance attribution as one connected system.

Prefer the simplest model that answers the practical question. Most useful first passes are linear or quadratic: regressions, factor decompositions, covariance models, mean-variance optimization, penalties, projections, and attribution decompositions.

## Workflow

1. Define the decision: asset universe, rebalance frequency, holding horizon, constraints, benchmark, and objective.
2. Separate forecasts: expected excess return, risk/covariance, transaction cost, and capacity.
3. Test alpha out of sample before optimizing: use time-respecting validation, walk-forward evaluation, and data-snooping checks.
4. Build or inspect the risk model: distinguish factor risk from idiosyncratic risk, and evaluate covariance quality with portfolio-level tests.
5. Convert forecasts into positions: use mean-variance logic, then add constraints, penalties, turnover control, and market-impact awareness.
6. Analyze realized performance: decompose PnL into factor, idiosyncratic, selection, sizing, timing, cost, and residual components.
7. Report uncertainty: call out estimation error, model instability, implementation assumptions, and whether observed results could be luck.

## Load References

Read only the files needed for the user request:

- `references/core-framework.md`: for setting up a complete quant research review or explaining the full investment process.
- `references/alpha-backtesting.md`: for alpha signals, predictive features, backtests, walk-forward tests, overfitting, skill vs luck, and information coefficient.
- `references/risk-factor-models.md`: for returns, volatility, covariance, fundamental factor models, statistical factor models, PCA, shrinkage, and hedging.
- `references/portfolio-construction.md`: for mean-variance optimization, constraints, penalties, capacity, market impact, Kelly sizing, and drawdown control.
- `references/performance-attribution.md`: for ex post analysis, factor/idiosyncratic attribution, selection vs sizing, and explaining realized PnL.

## Output Style

When answering analysis requests, produce decision-useful output:

- State the investment question being answered.
- List data and modeling assumptions.
- Give the recommended analysis path.
- Identify failure modes before conclusions.
- End with concrete next checks, metrics, or implementation steps.

Do not present backtest performance as evidence of edge unless the validation design, cost model, and multiple-testing risk have been addressed.
