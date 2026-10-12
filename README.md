# SPY 30-Day Momentum: Statistical Research and Robustness Analysis

## Research Objective

This project investigates whether SPY's previous 30-day return has a statistically significant linear relationship with its subsequent 30-day return.

The research evaluates the relationship using Pearson correlation, linear regression, quintile analysis, and robustness testing, with particular attention to the effects of overlapping observations on statistical inference.

## Research Hypothesis

- **Null hypothesis (H₀):** There is no linear relationship between previous and subsequent 30-day SPY returns.
- **Alternative hypothesis (H₁):** A nonzero linear relationship exists.
- **Significance level:** α = 0.05.

## Data and Methodology

- **Asset:** SPDR S&P 500 ETF Trust (SPY).
- **Historical period:** January 3, 2000 – December 31, 2025.
- **Data:** Adjusted closing prices retrieved using Yahoo Finance.
- **Momentum:** Previous 30-day return.
- **Forward return:** Subsequent 30-day return.

The analysis includes:

1. Pearson correlation and hypothesis testing.
2. Linear regression and coefficient of determination.
3. Reduced-overlap sampling to assess the sensitivity of conventional significance tests.
4. Exploratory quintile analysis to investigate possible nonlinear patterns.
5. Welch's t-test comparing the lowest-momentum quintile (Q1) against Q2–Q5.
6. Sensitivity analysis across 30 different sampling offsets.

## Key Results

| Analysis | Result | Interpretation |
|---|---|---|
| Full-sample Pearson correlation | r = −0.0914; p ≈ 1.72 × 10⁻¹³ | Weak negative correlation; conventional significance is affected by overlapping observations |
| Reduced-overlap correlation | r = −0.0920; p = 0.1780 | Weak negative correlation; insufficient evidence to reject H₀ |
| Linear regression | R² = 0.0083 | Approximately 0.83% of the observed forward-return variation explained |
| Reduced-overlap Welch test | p ≈ 0.0731 | Q1 versus Q2–Q5 difference is not significant at α = 0.05 |
| Offset sensitivity | 28/30 positive differences; 3/30 significant | Direction is relatively consistent, but statistical significance is not robust |

## Main Findings

The initial full-sample analysis suggested a statistically significant negative relationship between previous and subsequent 30-day SPY returns.

However, overlapping return windows created dependence between observations. After reducing overlap, the estimated correlation remained similar, but the statistical evidence became insufficient to reject the null hypothesis.

Exploratory quintile analysis suggested a possible reversal effect concentrated after strongly negative momentum observations. Nevertheless, Welch's test and sampling-offset sensitivity analysis did not establish a statistically robust effect.

## Limitations

- Reduced-overlap sampling does not guarantee fully independent observations.
- The quintile analysis was exploratory and was not independently validated out of sample.
- All sampling offsets originated from the same historical price series and therefore do not constitute independent confirmations.
- The project evaluates statistical relationships, not a fully implemented or validated trading strategy.
- Transaction costs, execution assumptions, and portfolio-level risk were not evaluated.

## Conclusion

The research identifies a weak negative linear relationship and a possible nonlinear reversal pattern concentrated after negative momentum.

However, the evidence is insufficient to establish a statistically reliable predictive signal.

The primary contribution is demonstrating how overlapping observations, sample construction, and robustness testing can materially affect statistical conclusions in financial time-series research.

## Technologies

Python, pandas, NumPy, SciPy, Matplotlib, yfinance, and Jupyter Notebook.

## Notebook

[View the complete research notebook](Project2_Momentum.ipynb)
