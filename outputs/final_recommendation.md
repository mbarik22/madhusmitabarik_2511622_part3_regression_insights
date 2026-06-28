# Final Business Recommendation

## Executive Summary

Based on regression analysis of 320 store-month observations across 80 stores, this report identifies the operational and contextual factors most strongly associated with monthly sales performance. The multiple regression model (R² = 0.821) reveals that **footfall, staffing levels, marketing investment, inventory availability, store type, and holiday timing** are the most important predictors of monthly sales revenue.

---

## 1. Which Factors Are Most Strongly Associated with Monthly Sales?

In order of statistical strength and practical magnitude:

### 1. Footfall (Customer Visits) — **Strongest Predictor**
- **Coefficient:** £28.14 per additional visitor  
- **R² in isolation:** 73.5%  
- **Significance:** p < 0.0001  
- Each additional 1,000 customer visits per month is associated with approximately **£28,140 in additional monthly sales**.  
- Footfall is by far the dominant driver of sales performance. Stores with high foot traffic consistently generate higher revenue regardless of other factors.

### 2. Staff Count — **Second Strongest Predictor**
- **Coefficient:** £2,860 per additional staff member  
- **Significance:** p = 0.029  
- A store with 5 additional staff members, on average, generates approximately **£14,300 more per month**.  
- This likely reflects that more staff enables better customer service, reduced wait times, and higher conversion of visits into purchases.

### 3. Marketing Spend — **Significant but Smaller Marginal Return**
- **Coefficient:** £1.14 per £1 spent  
- **Significance:** p < 0.0001  
- Marketing spend has a statistically significant and positive relationship with sales, but the return is modest: every £10,000 increase in monthly marketing budget is associated with approximately **£11,400 in additional sales** — a near break-even return at the top-line level.

### 4. Inventory Availability — **Operationally Significant**
- **Coefficient:** £2,937 per 1 percentage point increase  
- **Significance:** p < 0.0001  
- Improving stock fill rate by 5 percentage points is associated with approximately **£14,700 more in monthly sales**. Out-of-stock situations clearly cost the business revenue.

### 5. Store Type — **Structurally Important**
- Airport stores: **+£36,455/month** vs. Residential (p < 0.0001)  
- Mall stores: **+£26,864/month** vs. Residential (p < 0.0001)  
- High Street stores: **+£15,600/month** vs. Residential (p = 0.013)  
- Location and store format have a strong structural impact on sales that cannot be altered in the short term but should inform expansion and investment decisions.

### 6. Holiday Flag — **Moderate Seasonal Boost**
- **Coefficient:** £13,534 for months containing a public holiday  
- **Significance:** p = 0.045  
- Stores generate approximately £13,500 more in months with holidays — suggesting the importance of being prepared with stock and staffing during peak periods.

---

## 2. Which Variables Should Leadership Focus On?

**Act on these variables (they are statistically significant and operationally controllable):**

| Variable | Action |
|---|---|
| **Footfall** | Invest in location-based marketing, accessibility improvements, events, and community partnerships to increase visitor numbers |
| **Staff Count** | Avoid understaffing, particularly in higher-traffic or higher-type stores; model suggests the sales uplift from staffing is meaningful |
| **Marketing Spend** | Continue investing, but monitor ROI at store level — outlier high-spend months do not always produce proportional returns |
| **Inventory Availability** | Improve supply chain reliability; even a 5% uplift in stock fill rate predicts ~£14,700 more in monthly sales |
| **Holiday Planning** | Ensure full staffing and stock levels in months containing public holidays |

---

## 3. Which Variables Should NOT Be Over-Interpreted?

| Variable | Reason Not to Over-Interpret |
|---|---|
| **avg_discount_pct** | Coefficient is negative (−£60,186 per unit of discount proportion) but is **not statistically significant** (p = 0.110). Reducing discounts is not clearly supported by this data as a sales-growth lever. |
| **customer_rating** | Not significant in simple regression (p = 0.647). Customer ratings may affect long-run brand reputation, but this dataset shows no clear short-term linear relationship with monthly sales. |
| **competitor_distance_km** | Not statistically significant in any model tested. Distance to competitor alone does not reliably predict sales performance. |
| **Region dummies** | After controlling for store type and operational factors, regional differences were not statistically significant in this dataset. |
| **Marketing spend (outlier months)** | Several stores with very high marketing spend (>£100K/month) showed lower-than-expected sales. Marketing may exhibit **diminishing returns** at high investment levels. |

---

## 4. Recommended Business Actions

**Priority 1: Drive Footfall**  
Since footfall explains more than 73% of sales variance on its own, the highest-ROI investment the business can make is increasing customer visits. This includes:
- Local area marketing and events
- Store positioning near transport hubs (supporting Airport and Mall store type premiums)
- Loyalty programmes that increase repeat visit frequency

**Priority 2: Right-Size Staffing**  
The staffing coefficient (£2,860/staff member) is statistically significant. Leadership should audit stores that appear understaffed relative to their footfall and store type, and model the expected uplift from restoring optimal staffing levels.

**Priority 3: Protect Inventory Availability**  
A 5 percentage point increase in inventory availability predicts approximately £14,700 more in sales. This is an achievable operational target through improved demand forecasting and supplier management.

**Priority 4: Target Holiday Periods**  
The £13,534 holiday uplift is consistent. Stores should have proactive stock-up and staffing plans for months containing public holidays.

**Priority 5: Prioritise Store-Type Investments**  
When considering expansion or reallocation of capital, Airport and Mall formats appear to structurally outperform Residential stores by £26,000–£36,000 per month, after controlling for operational factors.

---

## 5. Risks and Limitations Leadership Should Keep in Mind

**Model limitations:**
- The dataset covers only **4 months** (Jan–Apr 2025) — seasonal trends beyond this window (e.g., summer or Christmas) are not captured.
- **80 stores** is a reasonable sample, but the model may not generalise perfectly to new stores in new markets.
- **14 records were excluded** due to missing data in customer_rating and competitor_distance_km — these stores are excluded from model estimates.

**Statistical limitations:**
- The model assumes a **linear relationship** between each predictor and sales. In reality, footfall may exhibit diminishing returns at very high levels (e.g., a store at capacity).
- **Multicollinearity** is possible between footfall and staff_count — stores that attract more visitors also tend to employ more staff, making it difficult to fully separate their effects.
- **avg_discount_pct** was not statistically significant. This does not mean discounting has no effect; it may be that the effect is non-linear, threshold-based, or confounded by store type.

---

## 6. Why Regression Shows Association, Not Causation

Regression analysis identifies variables that **move together** with monthly sales — but it cannot prove that changing one variable will cause a change in sales. Several reasons to be cautious:

- **Reverse causality:** Higher footfall may drive higher sales, but it is also possible that high-sales stores invest more in footfall-generating activities, making the relationship circular.
- **Omitted variables:** Factors not in the dataset — such as store management quality, local economic conditions, brand recognition, or historical catchment area demographics — may drive both footfall and sales simultaneously, creating a **spurious association**.
- **Selection bias:** The stores in this dataset are already in the retail chain's portfolio. The findings may not apply to stores in entirely new markets or formats.
- **Correlation is not intervention:** Even if footfall correlates strongly with sales (r = 0.858), artificially inflating footfall through unsustainable tactics (e.g., excessive discounting to attract visitors) may not generate the same sales uplift the model predicts.

**The correct framing for leadership:** The regression model provides evidence that increasing footfall, maintaining stock levels, and investing in marketing are **consistent with higher sales across this portfolio of stores**. These associations are strong enough to support investment decisions — but they should be validated through controlled pilots or A/B testing before large-scale rollout.

---

## Summary of Regression Evidence Supporting This Recommendation

| Claim | Supporting Evidence |
|---|---|
| Footfall is the primary driver | R² = 0.735 in isolation; coefficient = £28.14/visitor (p < 0.0001) |
| Staffing matters | £2,860/staff member, p = 0.029 |
| Marketing has positive returns | £1.14 per £1 spent, p < 0.0001; but diminishing at high spend |
| Inventory drives sales | £2,937 per 1% availability, p < 0.0001 |
| Airport/Mall stores outperform | +£36,455 and +£26,864 vs Residential (p < 0.0001) |
| Holiday uplift is real | +£13,534/holiday month, p = 0.045 |
| Discounting not proven to help | avg_discount_pct: p = 0.110 (not significant) |
| Overall model quality | Multiple R² = 0.821; Adjusted R² = 0.816 — strong predictive fit |
