# Portfolio Construction

Use this reference for mean-variance optimization, constraints, penalties, market impact, capacity, Kelly sizing, and drawdown control.

## Basic Setup

Portfolio construction converts forecasts into positions. Inputs usually include:

- Expected excess returns `mu`.
- Covariance matrix `Sigma`.
- Current holdings.
- Costs and market impact.
- Constraints: leverage, exposure, concentration, turnover, liquidity, borrow, and benchmark.
- Objective: maximize expected utility, Sharpe, information ratio, or benchmark-relative value.

## Mean-Variance Logic

The canonical objective is expected return minus risk penalty:

```text
maximize w' mu - lambda * w' Sigma w
```

This is useful because it gives a clear geometry: alphas are traded against risk, and factor exposures can be projected, neutralized, or intentionally retained.

Always ask how much estimation error is being amplified by optimization. Small alpha errors can create large position changes.

## Constraints And Penalties

Constraints are not magic alpha. They change the feasible set and often reduce theoretical efficiency. Use them because they encode real implementation limits or risk preferences.

Common constraints:

- Gross and net exposure.
- Factor neutrality or exposure bands.
- Sector, country, issuer, or asset concentration.
- Long-only, shorting, borrow, and locate constraints.
- Turnover and trade size limits.
- Liquidity and ADV participation limits.
- Benchmark-relative active weight or tracking error.

Prefer penalties when soft tradeoffs are more realistic than hard cutoffs:

- Turnover penalty.
- Factor exposure penalty.
- Concentration penalty.
- Market-impact penalty.
- Short-borrow penalty.

## Transaction Costs And Market Impact

A paper portfolio is not an investable portfolio until costs are included.

Cost model components:

- Spread and fees.
- Linear costs from commissions and expected slippage.
- Temporary market impact, often increasing nonlinearly with trade size.
- Permanent impact if trading reveals information or moves fair value.
- Borrow and financing costs.

Market impact makes multi-period optimization important. A fast-decaying alpha may justify higher turnover; a slow signal may require patient execution.

## Capacity

Capacity is the amount of capital that can be deployed before net performance degrades below target.

Capacity depends on:

- Signal turnover and decay.
- Liquidity of traded assets.
- Cross-sectional breadth.
- Concentration of positions.
- Cost and impact assumptions.
- Risk appetite and leverage.
- Whether alpha is shared by crowded strategies.

Report capacity alongside Sharpe. A high-Sharpe strategy with tiny capacity may still be useful, but it should not be presented like a scalable product.

## Kelly And Dynamic Risk Allocation

Kelly sizing links risk allocation to expected growth. In practice, use fractional Kelly because estimates are noisy and drawdowns matter.

Use Kelly-style reasoning when:

- Scaling a strategy based on estimated edge and risk.
- Comparing risk allocation across signals.
- Thinking about drawdown and ruin probability.

Be conservative:

- Use fractional Kelly.
- Stress alpha and volatility estimates.
- Cap leverage.
- Account for correlation between strategies.
- Evaluate drawdown under adverse regimes.

## Portfolio Review Checklist

- Does the portfolio's expected return come from intended signals?
- What are the largest factor exposures?
- Which constraints bind?
- How sensitive are weights to alpha and covariance changes?
- How much turnover is required?
- What is net performance after realistic costs?
- What is the capacity estimate?
- What happens if alpha is half as strong or risk is underestimated?
- Are positions explainable by signal strength, risk, and liquidity?
