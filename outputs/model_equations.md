# Model Equations and Strategic Performance Overview

This document defines the mathematical frameworks used to forecast monthly store sales, highlighting the transition from simple departmental metrics to a comprehensive, holistic store performance model.

## 1. Simple Regression Equations

These models provide tactical insight into standalone drivers but lack the complexity of a full retail operation.

*   **Footfall Impact Model:**
*   
    $$
    \text{Monthly Sales} = 175450 + 28.5 \times (\text{footfall})
    $$
    
    *Insight:* Every additional customer walking into a store generates approximately $28.50 in revenue.

---
*   **Marketing Spend Impact Model:**
*  Monthly Sales = 650200 + 1.45 × (marketing spend)

    
    *Insight:* Every $1.00 invested in marketing generates approximately $1.45 in incremental monthly sales.

## 2. Multiple Regression Equation (Final Model)

The multiple regression model provides the highest explanatory power (R squared = 84.34%) by integrating operational, geographic, and seasonal factors.

$$
\text{Monthly Sales} = 84083.44 - 11451.76(\text{Is East}) + 9325.09(\text{Is South}) + 12670.19(\text{Is West}) + 6225.45(\text{Is High Street}) + 29922.30(\text{Is Airport}) + 1.21(\text{marketing spend}) + 27.92(\text{footfall}) - 48050.16(\text{avg discount pct}) + 3157.36(\text{staff count}) + 2925.10(\text{inventory availability pct}) - 3230.37(\text{competitor distance km}) + 14269.14(\text{holiday flag}) + 11872.26(\text{customer rating})
$$

---

## 3. Variable Strategy and Explanations

### Dummy Variable Strategy
To include categorical variables, we used binary dummy encoding (0 or 1). To avoid the Dummy Variable Trap (perfect multicollinearity), we omitted one category from each set as the Reference Category:
*   **Region Reference Category:** North (All other regions are measured relative to North performance).
*   **Store Type Reference Category:** Mall and Residential (Pooled together as the baseline store type).

### Coefficient Explanations (Business Language)
*   **Location Impact:** Airport stores generate roughly $29,922 more in monthly sales compared to the baseline Mall/Residential stores.
*   **Operational Levers:** 
    *   **Staffing:** Increasing headcount by one staff member adds ~$3,157 to monthly revenue.
    *   **Inventory:** A 1% increase in inventory availability yields an additional ~$2,925.
    *   **Competition:** Every kilometer of distance from the nearest competitor adds ~$3,230 to monthly sales.
*   **Sentiment and Events:** Stores with a higher customer rating perform significantly better (+$11,872 per rating point), and holiday periods provide a distinct lift of ~$14,269.

---

## 4. Final Model Selection

**Selected Model:** Multiple Linear Regression.

**Reasoning:**
The Multiple Regression model was chosen over the simple models because it provides an integrated executive view of the business. While simple models accurately track single metrics like footfall, they fail to account for the interplay between operations, geography, and seasonality. With an explanatory power (R squared) of 84.34%, this model serves as a reliable decision-support tool.
