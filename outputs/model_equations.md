# Model Equations & Dummy Variable Strategy

## 📐 Dummy Variable Approach

To include the categorical variables `region` and `store_type` in our multiple linear regression model, they were converted into binary dummy variables (taking values of 0 or 1). 

To prevent perfect multicollinearity—a statistical issue known as the **Dummy Variable Trap**—we applied the $N-1$ rule. This means that for any categorical variable with $N$ unique groups, we only include $N-1$ dummy columns in the regression. Including all categories would make the columns perfectly predictable from one another, causing Excel's regression underlying mathematics to fail.

### 🌍 1. Regional Category Mapping
The `region` variable contains 4 distinct groups: East, North, South, and West.
* **Reference Category (Omitted):** `West`
* **Included Variables:** 
  * `Is_East` (1 if store is in the East, 0 otherwise)
  * `Is_North` (1 if store is in the North, 0 otherwise)
  * `Is_South` (1 if store is in the South, 0 otherwise)

*Interpretation:* If a store is located in the **West** region, all three dummy variables (`Is_East`, `Is_North`, `Is_South`) will equal `0`. The baseline intercept of the regression equation will inherently capture the performance of the West region.

### 🏪 2. Store Type Mapping
The `store_type` variable contains 4 distinct groups: Residential, High Street, Airport, and Mall.
* **Reference Category (Omitted):** `Mall`
* **Included Variables:**
  * `Is_Residential` (1 if Residential, 0 otherwise)
  * `Is_High_Street` (1 if High Street, 0 otherwise)
  * `Is_Airport` (1 if Airport, 0 otherwise)

*Interpretation:* If a store is a **Mall** type, all three store type dummy variables will equal `0`. The baseline performance of Mall stores is integrated directly into the main intercept.

---

## 📝 Theoretical Multiple Regression Equation

By removing the reference categories, our multiple linear regression model equation is structured as follows:

$$\text{Monthly Sales} = \beta_0 + \beta_1(\text{Marketing Spend}) + \beta_2(\text{Footfall}) + \beta_3(\text{Avg Discount Pct}) + \beta_4(\text{Staff Count}) + \beta_5(\text{Inventory Availability Pct}) + \beta_6(\text{Competitor Distance KM}) + \beta_7(\text{Holiday Flag}) + \beta_8(\text{Customer Rating}) + \beta_9(\text{Is East}) + \beta_{10}(\text{Is North}) + \beta_{11}(\text{Is South}) + \beta_{12}(\text{Is Residential}) + \beta_{13}(\text{Is High Street}) + \beta_{14}(\text{Is Airport})$$

*Where:*
* $\beta_0$ is the Intercept (representing a **Mall** store located in the **West** region).
* $\beta_1$ through $\beta_{14}$ represent the coefficients (slopes) that quantify the exact impact of each independent variable on `monthly_sales` when holding all other factors constant.
