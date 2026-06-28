# Retail Sales Performance Analysis: A Multiple Regression Approach

## Business Problem Summary
The objective of this project is to understand the drivers of monthly sales performance across various retail store locations. By identifying which operational and environmental factors (such as marketing spend, staffing levels, and location type) most significantly impact revenue, leadership can make data-driven decisions to optimize resource allocation, improve store profitability, and mitigate competitive threats.

## Dataset Description
The dataset contains performance metrics for 320 retail store observations. It includes operational inputs, geographic identifiers, and external environmental factors collected over a defined fiscal period.

## Dependent and Independent Variables
*   **Dependent Variable (Y):** `monthly_sales` (The primary revenue metric).
*   **Independent Variables (X):** 
    *   **Geographic:** `Is_East`, `Is_South`, `Is_West`, `Is_High_Street`, `Is_Airport`.
    *   **Operational:** `marketing_spend`, `footfall`, `staff_count`, `inventory_availability_pct`, `avg_discount_pct`, `competitor_distance_km`.
    *   **Contextual:** `holiday_flag`, `customer_rating`.

## Regression Approach
We employed a multi-stage modeling process, beginning with simple linear regressions to establish baselines for `footfall` and `marketing_spend`, followed by a comprehensive **Multiple Linear Regression** model. This allowed us to control for various confounding variables and isolate the net impact of each business driver.

## Dummy Variable Approach
To incorporate categorical data (Region and Store Type) into the regression, we used binary dummy encoding (0 or 1). To prevent the **Dummy Variable Trap** (perfect multicollinearity), we omitted one category from each set to serve as the **Reference Category**:
*   **Region:** `North` (Baseline).
*   **Store Type:** `Mall` & `Residential` (Baseline).

## Model Comparison Summary
The Multiple Linear Regression model significantly outperformed simple models, achieving an **$R^2$ of 84.34%**. While simple models provided tactical insights into specific drivers, the multiple regression model provided a holistic framework that accounted for operational, geographic, and seasonal interplay.

## Final Model Selected
**Multiple Linear Regression**
*   **Reasoning:** It explains 84.34% of the variation in monthly sales and provides actionable, statistically significant coefficients for key business levers like staffing, inventory availability, and competitive distance.

## Business Recommendation
1.  **Prioritize Operations:** Focus resources on maintaining high `inventory_availability_pct` and optimized `staff_count`, as these are proven revenue drivers.
2.  **Strategic Differentiation:** For stores in high-competition zones (low `competitor_distance_km`), emphasize service quality and customer rating to protect sales.
3.  **Refine Discounting:** Given that `avg_discount_pct` was not statistically significant, leadership should reassess the ROI of broad-based discounting strategies.

## Assumptions and Limitations
*   **Assumption:** The model assumes linear relationships between independent variables and sales.
*   **Limitation:** Regression shows *association*, not *causation*. Factors like `staff_count` might be higher because the store is already successful, rather than the other way around.
*   **Limitation:** Unquantifiable factors such as store management quality or localized economic shocks remain outside the model's scope.

## Screenshots
*   **Model Comparison:** [screenshots/model_comparison_preview.png](screenshots/model_comparison_preview.png)
*   **Residual Analysis:** [screenshots/residuals_preview.png](screenshots/residuals_preview.png)
