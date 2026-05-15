# SPX-Options-Greeks-ES-Delta-Hedging-and-Scenario-Analysis

## Project Objective

This project builds a market risk framework for SPX index options using the Black-Scholes model.

The goal is not to build a production-level pricing engine. The goal is to show how option prices and Greeks change across market inputs, and how Delta exposure can be hedged with ES futures while residual option risks remain.

## Workflow

1. Pull recent SPX market data.
2. Estimate 1-year historical volatility from daily SPX returns.
3. Build Black-Scholes pricing functions for European calls and puts.
4. Calculate Delta, Gamma, Vega, Theta, and Rho.
5. Analyze Greeks across strikes, maturities, and volatility assumptions.
6. Apply the Greeks framework to a real SPX call option chain.
7. Select a near-ATM SPX call and calculate portfolio Delta exposure.
8. Hedge the Delta exposure with ES futures.
9. Measure residual Greeks after the Delta hedge.
10. Run scenario analysis under SPX index shocks and volatility shocks.

## Key Risk Concepts

- Delta measures first-order directional exposure to SPX moves.
- Gamma measures how quickly Delta changes when SPX moves.
- Vega measures sensitivity to volatility shocks.
- Theta measures daily time decay.
- Rho measures interest-rate sensitivity.
- Delta-neutral does not mean risk-free because Gamma, Vega, Theta, and Rho exposures remain.

## Data and Assumptions

- Underlying index: SPX
- Market data source: Yahoo Finance via `yfinance`
- Historical volatility: estimated from 1-year SPX daily returns
- Option type: European-style SPX index option
- Dividend yield: set to `q = 0` as a simplification
- Risk-free rate: fixed at 4% in the model examples
- ES futures multiplier: 50 dollars per SPX index point
- SPX option multiplier: 100 dollars per SPX index point

## Main Takeaway

The project shows the full risk workflow: identify option exposures, calculate Greeks, hedge first-order Delta risk, measure residual Greeks, and stress test the hedged position under index and volatility shocks.
