# Model Equations & Dummy Variable Strategy

##  Dummy Variable Approach

To include the categorical variables `region` and `store_type` in our multiple linear regression model, they were converted into binary dummy variables (taking values of 0 or 1). 

To prevent perfect multicollinearity—a statistical issue known as the **Dummy Variable Trap**—we applied the $N-1$ rule. This means that for any categorical variable with $N$ unique groups, we only include $N-1$ dummy columns in the regression. Including all categories would make the columns perfectly predictable from one another, causing Excel's regression underlying mathematics to fail.

###  1. Regional Category Mapping
The `region` variable contains 4 distinct groups: East, North, South, and West.
* **Reference Category (Omitted):** `West`
* **Included Variables:** 
  * `Is_East` (1 if store is in the East, 0 otherwise)
  * `Is_North` (1 if store is in the North, 0 otherwise)
  * `Is_South` (1 if store is in the South, 0 otherwise)

*Interpretation:* If a store is located in the **West** region, all three dummy variables (`Is_East`, `Is_North`, `Is_South`) will equal `0`. The baseline intercept of the regression equation will inherently capture the performance of the West region.

###  2. Store Type Mapping
The `store_type` variable contains 4 distinct groups: Residential, High Street, Airport, and Mall.
* **Reference Category (Omitted):** `Mall`
* **Included Variables:**
  * `Is_Residential` (1 if Residential, 0 otherwise)
  * `Is_High_Street` (1 if High Street, 0 otherwise)
  * `Is_Airport` (1 if Airport, 0 otherwise)

*Interpretation:* If a store is a **Mall** type, all three store type dummy variables will equal `0`. The baseline performance of Mall stores is integrated directly into the main intercept.

---

## 🔢 Final Calculated Multiple Regression Equation

Based on our successful regression run, the final mathematical equation predicting monthly sales is:

Monthly Sales = 84,083.44 - 11,451.76(Is_East) + 9,325.09(Is_South) + 12,670.19(Is_West) + 6,225.45(Is_High_Street) + 29,922.30(Is_Airport) + 1.21(Marketing Spend) + 27.92(Footfall) - 48,050.16(Avg Discount Pct) + 3,157.36(Staff Count) + 2,925.10(Inventory Availability Pct) - 3,230.37(Competitor Distance KM) + 14,269.14(Holiday Flag) + 11,872.26(Customer Rating)
