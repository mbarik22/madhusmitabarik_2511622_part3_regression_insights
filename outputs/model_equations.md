# Model Equations

## Simple Regression Equations

### Simple Regression 1: Footfall → Monthly Sales

**Equation:**

```
monthly_sales = 447,699.03 + 35.64 × footfall
```

**Coefficient Explanation:**
- **Intercept (447,699.03):** The baseline monthly sales predicted when footfall is zero. This is a mathematical anchor — a store with zero visitors would theoretically still generate this figure based on the model, though in practice no store has zero footfall.
- **Footfall (35.64):** For every additional customer visit in a month, the model predicts monthly sales increase by approximately £35.64. This reflects the revenue value of each additional shopper attracted to the store.

**R² = 0.7348** — footfall alone explains 73.5% of variation in monthly sales.  
**p-value < 0.0001** — highly statistically significant.

---

### Simple Regression 2: Marketing Spend → Monthly Sales

**Equation:**

```
monthly_sales = 567,463.56 + 2.05 × marketing_spend
```

**Coefficient Explanation:**
- **Intercept (567,463.56):** Baseline sales when no marketing spend occurs. Some stores generate strong sales from established footfall and reputation alone.
- **Marketing Spend (2.05):** Each additional £1 spent on marketing is associated with approximately £2.05 in additional monthly sales. This represents a positive but modest return on marketing investment at the store level.

**R² = 0.1574** — marketing spend alone explains 15.7% of variation.  
**p-value < 0.0001** — statistically significant, but with limited standalone explanatory power.

---

## Multiple Regression Equation (Final Model)

**Equation:**

```
monthly_sales = 115,727.81
              + 28.14 × footfall
              + 2,859.69 × staff_count
              + 1.14 × marketing_spend
              − 60,186.23 × avg_discount_pct
              + 2,936.89 × inventory_availability_pct
              + 13,533.98 × holiday_flag
              + 36,455.13 × type_Airport
              + 15,599.94 × type_High_Street
              + 26,863.88 × type_Mall
```

**R² = 0.8210 | Adjusted R² = 0.8155 | F-statistic = 150.82 (p < 0.0001)**

---

## Coefficient Explanations (Multiple Regression)

| Variable | Coefficient | p-value | Business Meaning |
|---|---|---|---|
| Intercept | 115,727.81 | 0.012 | Baseline sales for a Residential store with all numerical predictors at zero |
| footfall | +28.14 | <0.0001 | Each additional visitor adds ~£28 in monthly sales, holding all else constant |
| staff_count | +2,859.69 | 0.029 | Each additional staff member is associated with ~£2,860 more in monthly sales |
| marketing_spend | +1.14 | <0.0001 | Each £1 of additional marketing is associated with £1.14 more in monthly sales |
| avg_discount_pct | −60,186.23 | 0.110 | Higher average discounts are negatively associated with sales, but this is **not statistically significant** — interpret with caution |
| inventory_availability_pct | +2,936.89 | <0.0001 | Each 1 percentage point increase in stock availability is associated with ~£2,937 more in monthly sales |
| holiday_flag | +13,533.98 | 0.045 | Months containing a public holiday generate approximately £13,534 more in sales on average |
| type_Airport | +36,455.13 | <0.0001 | Airport stores generate ~£36,455 more per month than equivalent Residential stores |
| type_High_Street | +15,599.94 | 0.013 | High Street stores generate ~£15,600 more per month than equivalent Residential stores |
| type_Mall | +26,863.88 | <0.0001 | Mall stores generate ~£26,864 more per month than equivalent Residential stores |

---

## Dummy Variable Explanation

### Variable Encoded: `store_type`

The `store_type` column is categorical with four values:
- Residential
- High Street
- Airport
- Mall

To include this in regression, three binary dummy variables were created — one for each category except the **reference category**.

### Reference Category: Residential

**Why Residential?**
- It is the most common store type in the dataset (100 observations).
- All other store types' coefficients represent their **premium or deficit relative to a Residential store**, controlling for all other variables.
- Using Residential as a base makes business sense since it represents the "default" or lowest-performing store type.

**Dummy Variables Created:**

| Variable | Value = 1 | Value = 0 |
|---|---|---|
| `type_Airport` | Store is an Airport store | Store is any other type |
| `type_High_Street` | Store is a High Street store | Store is any other type |
| `type_Mall` | Store is a Mall store | Store is any other type |

When all three dummies are 0, the store is classified as **Residential** — the reference category. This is standard practice in dummy variable regression to avoid perfect multicollinearity (the "dummy variable trap").

**Interpretation example:**  
A Mall store with identical footfall, staffing, and marketing spend to a Residential store is predicted to generate approximately **£26,864 more in monthly sales**, purely due to the Mall store-type advantage (e.g., higher footfall potential, captive audience, longer dwell time).

---

## Final Model Selected

**Selected Model:** Multiple Regression (9 predictors, R² = 0.821)

**Reason for Selection:**
1. **Best explanatory power** — explains 82.1% of variation versus 73.5% (footfall only) or 15.7% (marketing only).
2. **Captures multiple business levers** — footfall, staffing, marketing, inventory, holidays, and store type all contribute, giving leadership more actionable inputs.
3. **Good statistical fit** — Adjusted R² of 0.8155 confirms the model is not over-fitted; adding variables meaningfully improves prediction.
4. **Business relevance** — the model's significant coefficients all make intuitive commercial sense (more footfall, better stock, right location → more sales).
5. **Actionable for leadership** — the coefficients provide a basis for estimating the expected return from operational investments.
