# Project Name: Retail Sales Regression Analysis & Business Insights

## Task 1: Dataset Characterization & Variable Mapping

### 1. Dependent Variable (Target)
*   `Monthly_Sales` (or equivalent revenue column): This is the primary metric we want to predict and optimize.

### 2. Potential Independent Variables (Predictors)
*   **Marketing Spend:** Budget allocated to local advertising.
*   **Inventory Availability:** In-stock percentages or product depth metrics.
*   **Discount Percentage:** Average markdown or promotional rate applied.
*   **Staffing Levels:** Headcount or labor hours allocated per store.
*   **Store Type / Region:** Categorical identifiers capturing demographic or structural differences.

### 3. Variable Categorization
*   **Numerical Variables:** Marketing Spend, Inventory Availability, Discount Percentage, Staffing Levels.
*   **Categorical Variables:** Store Type (e.g., Flagship, Express), Region (e.g., North, South).

### 4. Cleaning & Transformations Required
*   **Missing Values:** Check for null entries in critical operational metrics.
*   **Categorical Encoding:** Convert text fields (Store Type, Region) into $0$ and $1$ binary numerical formats (Dummy Variables) for the multiple regression model.
*   **Outlier Detection:** Review extreme values in sales or discounts that could skew linear coefficients.

### 5. Variables Excluded from Regression
*   `Store_ID` / `Month`: Unique identifiers or simple indexing variables that do not carry structural predictive weight.
