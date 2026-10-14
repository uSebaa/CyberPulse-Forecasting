# CyberPulse — Final Forecasting Report

## 1. Recommendation

Chronos2 is recommended for forecasting hourly network flow counts because it achieved lower forecasting errors than the Seasonal Naive baseline across five rolling backtesting windows.

## 2. Evaluation Results

We used expanding-window rolling backtesting with five windows, a 24-hour forecast horizon, and a 24-hour step. Both models were evaluated on the same forecast periods.

| Model | MASE | Scaled CRPS (Approx.) | 80% Coverage |
|---|---:|---:|---:|
| Seasonal Naive | 1.059 | 0.907 | 77.5% |
| Chronos2 | 0.717 | 0.575 | 62.5% |

Chronos2 achieved better point forecasting accuracy (MASE) and probabilistic forecasting quality (approximate scaled CRPS).

However, Seasonal Naive provided more reliable prediction intervals.

## 3. Prediction Intervals

Chronos2 produced narrower 80% prediction intervals, with an average width of 32.64 flows compared with 50.36 flows for Seasonal Naive.

However, Chronos2 achieved only 62.5% empirical coverage against the expected 80%. Seasonal Naive achieved 77.5%.

Therefore, Chronos2's prediction intervals are too narrow and should not be considered well-calibrated.

## 4. Residual Analysis

Chronos2 residuals fluctuated around zero, with several large positive errors toward the end of the held-out period.

Most residual autocorrelations remained within the confidence bounds, suggesting no strong remaining short-lag autocorrelation.

The model underestimated some sudden increases in network flow counts, suggesting that irregular traffic spikes were not fully captured.

## 5. Model Selection

AutoGluon evaluated eight models using one internal validation window.

Chronos2 achieved the best internal validation score, tied with WeightedEnsemble.

Theta performed best on the held-out 24-hour test period. This difference demonstrates that a single holdout is insufficient to establish consistent model superiority.

The rolling backtesting comparison provides stronger evidence for Chronos2's performance against the benchmark models tested.

## 6. Limitations

The dataset contains sampled network flow records covering approximately one month.

The results should not be interpreted as evidence of real-world cyberattack detection.

Scaled CRPS was approximated using nine forecast quantiles.

## 7. Next Step

Calibrate Chronos2 prediction intervals using historical rolling backtesting errors to improve empirical coverage toward the nominal 80%, without using future observations.
