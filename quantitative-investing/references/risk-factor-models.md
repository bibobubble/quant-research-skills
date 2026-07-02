# Risk And Factor Models

Use this reference for returns, volatility, covariance, factor models, PCA/statistical factors, shrinkage, and hedging.

## Returns And Volatility

Define returns consistently:

- Simple return for portfolio accounting.
- Log return for additive time-series modeling when appropriate.
- Excess return relative to cash, benchmark, or hedge.
- Currency-adjusted return when assets trade in different currencies.

Financial returns commonly show fat tails, volatility clustering, time-varying correlations, and regime behavior. Volatility estimates should usually be reactive enough for current risk but stable enough to avoid noisy turnover.

Useful volatility tools:

- EWMA for simple reactive variance estimates.
- GARCH-style models for conditional heteroskedasticity.
- Realized volatility when high-frequency data is reliable.
- State-space or Kalman-style models when latent variance dynamics matter.

## Linear Factor Model

A common return model is:

```text
r = X f + epsilon
```

where `X` is the exposure/loading matrix, `f` is factor return, and `epsilon` is idiosyncratic return.

Use factor models to:

- Forecast and decompose risk.
- Attribute performance.
- Neutralize unwanted exposures.
- Build factor-mimicking portfolios.
- Separate systematic bets from idiosyncratic alpha.

## Fundamental Factor Models

Use when factors have economic labels such as market, industry, country, style, value, size, momentum, quality, volatility, liquidity, or currency.

Key checks:

- Exposure construction: timestamped, point-in-time, winsorized if needed.
- Identifiability: avoid rank-deficient or collinear exposures without constraints.
- Factor covariance: shrink noisy estimates and monitor regime changes.
- Idiosyncratic risk: estimate robustly; inspect clusters and off-diagonal residual correlation.
- Model turnover: exposures and predicted risk should not jump without cause.
- Beta tests: realized asset returns should align with predicted factor exposures.

## Statistical Factor Models

Use PCA, SVD, or related low-rank approximations when common structure should be learned from returns rather than specified through known exposures.

Key checks:

- Choose number of factors with stability and out-of-sample risk performance, not only in-sample variance explained.
- Shrink eigenvalues when sample size is small relative to universe size.
- Control eigenvector turnover to avoid unstable portfolios.
- Interpret components through clustering, regression on known factors, and exposure concentration.
- Beware of components that are artifacts of missing data, stale prices, or liquidity groups.

## Covariance Evaluation

Do not evaluate covariance models only by element-wise fit. Evaluate how they behave in portfolio use:

- Minimum-variance portfolio realized risk.
- Predicted versus realized portfolio volatility.
- Factor exposure and risk decomposition.
- Mahalanobis distance behavior.
- Stability of inverse covariance or precision matrix.
- Sensitivity of optimized weights to small changes in inputs.

## Hedging

Before hedging, define what risk should remain:

- Hedge market beta, sector/country/style exposure, currency, rate, commodity, or tradable factor risk.
- Use factor hedging when exposures are cross-sectional.
- Use time-series beta hedging when hedge instruments are tradable return series.
- Recheck whether the hedge introduces cost, basis risk, liquidity risk, or crowding.

## Common Failure Modes

- Using a covariance matrix that is mathematically valid but economically unstable.
- Overfitting the precision matrix and creating extreme optimized weights.
- Treating PCA components as meaningful without interpretation.
- Ignoring idiosyncratic residual correlation.
- Using stale or future factor exposures.
- Hedging away the intended alpha.
