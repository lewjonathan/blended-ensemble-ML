# Ensemble ML Alpha Model

This project explores ensemble-based classification for short-horizon equity index direction using a combination of machine learning models.

The focus is on evaluating whether ensemble methods can produce more stable signals under time-series constraints and out-of-sample testing.

## Results Summary

Out-of-sample evaluation highlights several key observations:

- Ensemble models achieved higher AUC than individual base learners, indicating improved ranking ability
- Despite higher AUC, probability-based aggregation often resulted in fewer trades under fixed thresholds
- Simple averaging across models produced more consistent signals across time periods

## Backtest Results (Out-of-Sample)

- Benchmark (SPY):
  - Total Return: ~32%
  - Volatility: ~17%
  - Sharpe Ratio: ~0.8

- Ensemble Strategy (baseline):
  - Produced positive but inconsistent returns across time windows
  - Performance sensitive to thresholding and signal filtering

- Ensemble with confidence filtering:
  - Total Return: ~40–50% range depending on configuration
  - Volatility: ~13–15%
  - Sharpe Ratio: ~1.4–1.6 in stronger configurations

## Backtest Observations

- Individual models showed unstable performance across time splits
- Ensemble methods improved stability but did not eliminate fragility
- Increasing thresholds reduced turnover but also reduced opportunity
- Transaction costs materially impacted net performance
- Volatility targeting improved drawdown control but did not consistently improve Sharpe

## Interpretation

- Most of the apparent “edge” is conditional and regime-dependent
- Ensemble methods improve robustness but do not create standalone alpha
- A large portion of performance comes from signal filtering and risk controls
- Signal generation alone is insufficient without disciplined portfolio construction

## Caveats

- Results depend on feature construction and sample period
- Performance varies significantly across configurations
- No claim of persistent alpha — results are conditional
- Simplified execution assumptions relative to real trading environments

## What is included

- Time-series train / validation / test split
- Multiple model training and ensemble aggregation
- Out-of-sample evaluation
- Basic backtesting layer
- Sensitivity testing across thresholds and configurations

## Research focus

The implementation emphasizes:

- leakage-aware validation
- model comparison under consistent splits
- robustness over peak performance
- simplicity over overfitting

## Implementation Notes

- Time-series cross-validation
- Out-of-sample testing without refitting
- Binary classification framework
- Simplified transaction cost assumptions

Focus is placed on understanding model behavior rather than maximizing reported performance.

## File

- `Ensemble_ML_github.py` — core research pipeline
