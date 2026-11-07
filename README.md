# Udacity A/B Testing — Product Experiment Analysis

## Business Problem

Udacity tested an additional screening question during free-trial enrollment to discourage users who were unlikely to complete their trial and become paying customers.

**Objective:** Determine whether the screening question reduces unnecessary trial enrollments without materially harming paid conversions.

## Dataset

[Interactive Kaggle notebook](https://www.kaggle.com/code/zacksshen/udacity-ab-testing-by-google) is a reference implementation, not the author's analysis. The notebook in this repository contains the independent analysis.

Source: [Udacity A/B Testing by Google — Kaggle](https://www.kaggle.com/datasets/zacksshen/udacity-ab-testing-by-google-datasets)

The dataset contains 37 days of aggregated control and experiment observations, with 23 days containing complete enrollment and payment outcomes.

This is an educational version of a real Udacity experiment with modified figures.

## Methodology

- Defined gross conversion, net conversion, and trial-to-payment metrics.
- Checked traffic allocation and click-through-rate consistency.
- Performed two-proportion Z-tests.
- Calculated 95% confidence intervals using the Newcombe method.
- Evaluated business trade-offs through hypothetical cost sensitivity analysis.

## Results

| Metric | Treatment Effect | Statistical Finding |
|---|---|---|
| Gross Conversion | −2.06 percentage points | Significant (p < 0.001) |
| Net Conversion | −0.49 percentage points | Not significant (p = 0.156) |
| Trial-to-Payment Rate | +3.11 percentage points | Descriptive; subject to selection effects |

The 95% confidence interval for net conversion was **−1.16 to +0.19 percentage points**.

## Visualizations

<img width="889" height="490" alt="download" src="https://github.com/user-attachments/assets/2e02b4b2-90c9-44b2-9b5c-81dc415e22f7" />


<img width="890" height="490" alt="download" src="https://github.com/user-attachments/assets/d2b11faf-9c6c-4a76-9cf8-fb9940cb7875" />

## Business Recommendation

**Hold the full rollout.**

The screening question significantly reduced free-trial enrollment, but the available evidence does not establish that paid conversions are preserved within an acceptable business threshold.

Before launching, the company should validate actual trial costs, customer contribution margins, and acceptable losses in paid conversion.

## Limitations

- Aggregated daily observations rather than user-level records.
- Financial assumptions are illustrative, not actual Udacity costs.
- No direct measurement of customer satisfaction or long-term educational outcomes.
- Higher trial-to-payment conversion does not establish a causal improvement among trial participants.

## Reproduce

1. Open the notebook in Kaggle and attach the [Udacity A/B Testing by Google dataset](https://www.kaggle.com/datasets/zacksshen/udacity-ab-testing-by-google-datasets).
2. Run all cells in order. Results use 23 days with complete enrollment and payment follow-up; 37 days are available for pageview/click checks.
3. The last cells generate the conversion and confidence-interval figures.

## Tools

Python, Pandas, NumPy, SciPy, Statsmodels, Matplotlib.

## Conclusion

This project demonstrates how statistical experimentation, product metrics, and economic reasoning can inform a product-launch decision under uncertainty.
