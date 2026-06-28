# Model Comparison

## Overview

Three regression models were built and compared to identify which approach best explains variation in monthly sales across stores.

---

## Model 1: Simple Regression — Footfall

| Item | Detail |
|---|---|
| **Model Name** | Simple Regression 1 — Footfall |
| **Dependent Variable** | monthly_sales |
| **Independent Variable** | footfall |
| **Intercept** | 447,699.03 |
| **Coefficient (footfall)** | 35.64 |
| **R²** | 0.7348 |
| **Adjusted R²** | 0.7340 |
| **F-statistic** | 842.49 |
| **F p-value** | < 0.0001 |
| **Coefficient p-value** | < 0.0001 |

**Significant Variables:** footfall (p < 0.0001)

**Business Usefulness:** Highly useful. Footfall alone explains 73.5% of monthly sales variation. This confirms that foot traffic is the single most important driver of sales. Leadership can use this to prioritise store locations, accessibility improvements, and traffic-building campaigns.

**Limitations:** Ignores staffing, marketing investment, store characteristics, and seasonal effects. A single-variable model oversimplifies complex retail dynamics.

---

## Model 2: Simple Regression — Marketing Spend

| Item | Detail |
|---|---|
| **Model Name** | Simple Regression 2 — Marketing Spend |
| **Dependent Variable** | monthly_sales |
| **Independent Variable** | marketing_spend |
| **Intercept** | 567,463.56 |
| **Coefficient (marketing_spend)** | 2.05 |
| **R²** | 0.1574 |
| **Adjusted R²** | 0.1547 |
| **F-statistic** | 56.80 |
| **F p-value** | < 0.0001 |
| **Coefficient p-value** | < 0.0001 |

**Significant Variables:** marketing_spend (p < 0.0001)

**Business Usefulness:** Moderately useful as a standalone signal. The model shows that marketing spend is positively associated with sales, but explains only 15.7% of variation when used alone. Marketing clearly matters, but its effect is much smaller than footfall and staffing.

**Limitations:** R² is low — many other factors drive sales. Marketing spend on its own is not a reliable sales predictor. High-spend periods may coincide with promotions that don't translate directly to revenue.

---

## Model 3: Multiple Regression — Key Predictors (Final Model)

| Item | Detail |
|---|---|
| **Model Name** | Multiple Regression — Combined Model |
| **Dependent Variable** | monthly_sales |
| **Independent Variables** | footfall, staff_count, marketing_spend, avg_discount_pct, inventory_availability_pct, holiday_flag, type_Airport, type_High_Street, type_Mall |
| **Intercept** | 115,727.81 |
| **R²** | 0.8210 |
| **Adjusted R²** | 0.8155 |
| **F-statistic** | 150.82 |
| **F p-value** | < 0.0001 |

### Coefficients and Significance

| Variable | Coefficient | p-value | Significant? |
|---|---|---|---|
| footfall | 28.14 | < 0.0001 | ✅ Yes |
| staff_count | 2,859.69 | 0.029 | ✅ Yes |
| marketing_spend | 1.14 | < 0.0001 | ✅ Yes |
| avg_discount_pct | −60,186.23 | 0.110 | ❌ No |
| inventory_availability_pct | 2,936.89 | < 0.0001 | ✅ Yes |
| holiday_flag | 13,533.98 | 0.045 | ✅ Yes |
| type_Airport | 36,455.13 | < 0.0001 | ✅ Yes |
| type_High_Street | 15,599.94 | 0.013 | ✅ Yes |
| type_Mall | 26,863.88 | < 0.0001 | ✅ Yes |

**Business Usefulness:** This is the strongest and most complete model, explaining 82.1% of variation in monthly sales. It captures the combined effect of operational factors (footfall, staff, marketing, inventory), timing (holidays), and store characteristics (type). This model is the most actionable for leadership.

**Limitations:** avg_discount_pct is not statistically significant, suggesting discounting may not directly drive top-line sales in this dataset. The model cannot capture store-specific history, brand reputation, or local economic conditions.

---

## Side-by-Side Comparison

| Criterion | Simple 1 (Footfall) | Simple 2 (Marketing) | Multiple (Final) |
|---|---|---|---|
| R² | 0.7348 | 0.1574 | **0.8210** |
| Adjusted R² | 0.7340 | 0.1547 | **0.8155** |
| # Predictors | 1 | 1 | 9 |
| Significant Vars | 1 | 1 | 7 |
| F-statistic | 842.49 | 56.80 | **150.82** |
| Business Completeness | Partial | Partial | **Full** |
| Interpretability | High | High | Medium |
| Recommended for action? | Partial only | No | ✅ Yes |

---

## Conclusion

The **Multiple Regression Model** is selected as the final model. It provides the best explanatory power (R² = 0.821) and incorporates all key business levers that leadership can act on. The simple footfall model is also valuable as a quick diagnostic tool for assessing store traffic performance.
