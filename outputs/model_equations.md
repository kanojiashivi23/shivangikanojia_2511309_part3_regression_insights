# Store Performance Model Equations & Selection

This document outlines the mathematical models developed to understand and predict store revenue. The formulas translate our raw operational data into actionable business levers.

## 1. Simple Regression Equations
Simple regression models help us understand the isolated impact of a single business driver on monthly sales.

**Model A: Footfall Impact**
$$
\text{Monthly Sales} = 446,410.58 + 35.68(\text{footfall})
$$
* **Business Translation:** Before a single customer walks in, a store's baseline revenue stands at $446,410.58. For every additional customer that enters the store, revenue increases by an average of $35.68.

**Model B: Marketing Spend Impact**
$$
\text{Monthly Sales} = 560,777.35 + 2.13(\text{marketing\_spend})
$$
* **Business Translation:** Without any marketing, a store generates a baseline of $560,777.35. For every $1 added to the local marketing budget, the store yields an expected return of $2.13 in sales.

---

## 2. Multiple Regression Equation
The multiple regression model provides a holistic view of the business by evaluating all operational and environmental factors simultaneously. 

$$
\begin{aligned}
\text{Monthly Sales} = \; & 84,083.44 - 11,451.76(\text{Is\_East}) + 9,325.09(\text{Is\_South}) + 12,670.19(\text{Is\_West}) \\
& + 6,225.45(\text{Is\_High\_Street}) + 29,922.30(\text{Is\_Airport}) + 1.21(\text{marketing\_spend}) \\
& + 27.92(\text{footfall}) - 48,050.16(\text{avg\_discount\_pct}) + 3,157.36(\text{staff\_count}) \\
& + 2,925.10(\text{inventory\_availability\_pct}) - 3,230.37(\text{competitor\_distance\_km}) \\
& + 14,269.13(\text{holiday\_flag}) + 11,872.26(\text{customer\_rating})
\end{aligned}
$$

### Explanation of Coefficients (Business Impact)
Each coefficient represents the change in monthly sales when that specific factor increases by one unit, assuming all other operational factors remain identical.
* **Baseline (Intercept: 84,083.44):** The theoretical starting revenue for a baseline store (North region, Mall/Residential type) when all operational metrics are zero.
* **marketing_spend (1.21):** Every $1 spent on marketing generates $1.21 in sales when accounting for all other factors.
* **footfall (27.92):** Each additional visitor contributes roughly $27.92 to revenue.
* **avg_discount_pct (-48,050.16):** Heavy discounting hurts the top line; a full 100% discount rate logically wipes out revenue, but practically, moving the average discount rate up by 1% drops revenue by roughly $480.50. 
* **staff_count (3,157.36):** Adding one more employee to the floor drives an additional $3,157.36 in monthly sales, likely through better customer service and faster checkout times.
* **inventory_availability_pct (2,925.10):** Improving shelf-stocking rates by 1% secures an extra $29.25 in sales by preventing missed opportunities from stock-outs.
* **competitor_distance_km (-3,230.37):** Every kilometer further away a competitor is positioned surprisingly drops sales by $3,230.37, suggesting our stores perform better in dense retail hubs where competitor proximity actually draws a larger shared crowd.
* **holiday_flag (14,269.13):** Operating during a recognized holiday period guarantees an automatic $14,269.13 revenue bump.
* **customer_rating (11,872.26):** Improving the store's average rating by a full 1.0 star increases monthly sales by $11,872.26, proving that customer satisfaction has a direct financial return.

---

## 3. Dummy Variables & Reference Categories
Statistical models cannot read text categories like "East" or "Airport." We convert these into binary (0 or 1) "dummy variables" to measure their structural impact. To prevent the model from breaking due to redundancy (the Dummy Variable Trap), one category from each group is omitted and serves as the invisible baseline.

**Regional Baseline:**
* **Reference Category:** North Region.
* **Interpretation:** The model evaluates East (-$11,451.76), South (+$9,325.09), and West (+$12,670.19) *compared to* the North. If a store is in the West, it naturally earns $12,670.19 more than an identical store in the North.

**Store Type Baseline:**
* **Reference Category:** Mall & Residential Stores.
* **Interpretation:** Airport stores hold a massive locational advantage, driving a $29,922.30 premium over standard Mall/Residential stores, likely due to a captive audience with high impulse-buying behavior. High Street locations offer a milder $6,225.45 premium over the baseline.

---

## 4. Final Model Selection
**Selected Model:** The Multiple Linear Regression Model.

**Reasoning:**
Relying on the simple regression models is functionally identical to managing a store by only tracking the door counter or only looking at the ad budget. The simple footfall model ignores whether the store is actually staffed to handle the traffic, and the simple marketing model suffers from severe omitted variable bias. 

The **Multiple Regression Model** is the definitive choice because it captures the complex reality of store operations. Explaining over 84% of the variance in revenue, it equips leadership with a multidimensional toolkit. It reveals exactly how to balance the marketing budget, optimize headcount on the floor, and prioritize inventory availability to maximize profitability across different regions and store types.
