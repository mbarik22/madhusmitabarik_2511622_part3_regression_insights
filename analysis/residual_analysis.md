# Residual Analysis

## Overview

Residuals are the difference between a store's **actual monthly sales** and what our final multiple regression model **predicted** for that store and month. Analysing residuals helps identify stores that consistently outperform or underperform model expectations.

**Formula:** `Residual = Actual Monthly Sales − Predicted Monthly Sales`

**Model used:** Multiple Regression (R² = 0.821)  
**Predictors:** footfall, staff_count, marketing_spend, avg_discount_pct, inventory_availability_pct, holiday_flag, store_type dummies

---

## Top 5 Largest Positive Residuals (Model Under-Predicts)

These stores performed **better than expected** given their operational characteristics.

| Store ID | Month | Store Type | Region | Actual Sales (£) | Predicted Sales (£) | Residual (£) |
|---|---|---|---|---|---|---|
| STR-1030 | Feb 2025 | Residential | West | 820,519 | 710,671 | **+109,848** |
| STR-1028 | Apr 2025 | Mall | East | 713,611 | 617,261 | **+96,350** |
| STR-1026 | Apr 2025 | Mall | East | 625,514 | 532,993 | **+92,521** |
| STR-1051 | Feb 2025 | Airport | East | 787,716 | 695,560 | **+92,155** |
| STR-1050 | Apr 2025 | Residential | North | 735,787 | 647,005 | **+88,782** |

### Business Interpretation — Positive Residuals

Stores with large positive residuals are **outperforming what the model predicts** based on their observable characteristics. This could mean:

- **STR-1030 (West, Residential):** This store significantly exceeded expectations in February. Possible causes include local events, a particularly strong promotion, or an operational advantage not captured in the data (e.g., store refurbishment, local community partnerships).
- **STR-1028 and STR-1026 (Mall, East):** Mall stores in the East appear to have outperformed their predicted values, suggesting the model may underestimate Mall performance in the East region, or these stores benefited from temporary boosts.
- **STR-1051 (Airport, East):** Airport stores generally command a premium (reflected in the Airport dummy), but this store exceeded even that adjusted benchmark — possibly driven by seasonal travel demand.
- **STR-1050 (Residential, North):** A consistently strong performer, suggesting store-specific factors (management quality, loyal customer base) that the model cannot capture.

**Overall signal:** Leadership should investigate what these top outperforming stores are doing differently. Positive residuals can reveal best practices worth replicating.

---

## Top 5 Largest Negative Residuals (Model Over-Predicts)

These stores performed **worse than expected** given their observable characteristics.

| Store ID | Month | Store Type | Region | Actual Sales (£) | Predicted Sales (£) | Residual (£) |
|---|---|---|---|---|---|---|
| STR-1017 | Mar 2025 | High Street | West | 685,379 | 848,036 | **−162,657** |
| STR-1012 | Jan 2025 | Residential | West | 595,468 | 722,841 | **−127,374** |
| STR-1023 | Feb 2025 | Mall | South | 627,172 | 744,947 | **−117,775** |
| STR-1001 | Apr 2025 | Residential | East | 658,920 | 758,353 | **−99,433** |
| STR-1007 | Feb 2025 | Mall | West | 800,452 | 897,992 | **−97,540** |

### Business Interpretation — Negative Residuals

Stores with large negative residuals are **underperforming relative to their operational inputs**. Given the footfall, staffing, and marketing spend invested, these stores should theoretically be generating more revenue. Possible explanations:

- **STR-1017 (High Street, West — March 2025):** Largest negative residual. Despite having the inputs the model expects to generate ~£848K, this store only achieved £685K. This may reflect local competition, poor execution, or unusual external disruption (e.g., road closures near a High Street store).
- **STR-1012 (Residential, West — Jan 2025):** Likely impacted by low post-Christmas demand; the model may not fully adjust for this seasonal dip.
- **STR-1023 (Mall, South — Feb 2025):** Very high marketing spend (£141,540) was recorded this month but did not translate to the expected sales uplift — possible marketing inefficiency or misalignment between campaign timing and shopper behaviour.
- **STR-1001 (Residential, East — April 2025):** Consistently appearing in negative territory across months, suggesting a persistent structural underperformance that leadership should investigate.
- **STR-1007 (Mall, West — Feb 2025):** Unusually high marketing spend (£172,416) in this month but below-predicted sales, again suggesting a high-spend low-return scenario.

---

## Model Under-Prediction vs Over-Prediction Patterns

| Pattern | Observation |
|---|---|
| Under-prediction | Airport and some Mall stores tend to outperform the model — their premium location advantage may be larger than the dummy variable captures |
| Over-prediction | Some West-region stores underperform despite high inputs — regional market saturation or competition may not be fully captured |
| High marketing, low return | Stores with marketing_spend outliers (e.g., >£120K/month) tend to produce larger negative residuals — marketing may exhibit diminishing returns |
| Residential stores | Show a wide spread of residuals — these stores are more heterogeneous than the model assumes |

---

## Conclusion

The residual analysis reveals that while the model explains 82.1% of variation, there remain meaningful unexplained differences across stores. Leadership should:

1. **Investigate top outperforming stores** to identify transferable practices.
2. **Probe high-residual underperformers** for operational or local market issues.
3. **Revisit marketing ROI** for stores with very high spend but low residuals — returns appear to diminish above a threshold.
4. **Consider store-specific fixed effects** in future modelling to control for persistent store-level characteristics not captured in the current dataset.
