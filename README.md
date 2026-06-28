# Retail Sales Performance Analysis

## Business Problem Summary
We analyzed retail sales performance to identify key drivers of revenue. By understanding which factors (footfall, marketing, staffing) impact `monthly_sales`, we aim to provide actionable insights for resource allocation and store profitability.

## Dataset Description
The dataset contains 320 records of store performance, including operational metrics, geographic locations, and external environmental factors.

## Dependent and Independent Variables
*   **Dependent Variable (Y):** `monthly_sales`
*   **Independent Variables (X):** Geographic dummies (`Is_East`, `Is_South`, `Is_West`, `Is_High_Street`, `Is_Airport`), `marketing_spend`, `footfall`, `avg_discount_pct`, `staff_count`, `inventory_availability_pct`, `competitor_distance_km`, `holiday_flag`, `customer_rating`.

## Regression Approach
We used both Simple Linear Regression (to test individual drivers) and Multiple Linear Regression (to isolate the impact of multiple variables simultaneously).

## Dummy Variable Approach
Categorical variables were converted to binary (0/1) indicators. We used `North` (Region) and `Mall/Residential` (Store Type) as the **Reference Categories** to avoid the dummy variable trap.

## Model Comparison Summary
The Multiple Regression model achieved an $R^2$ of 84.34%, significantly outperforming the simple regression models which had lower explanatory power.

## Final Model Selected
**Multiple Linear Regression** was selected because it accounts for operational, geographic, and seasonal factors, providing a comprehensive view of business drivers.

## Business Recommendation
Leadership should prioritize **inventory availability** and **staffing levels** to boost revenue. Broad discounting strategies should be re-evaluated as they lacked statistical significance in our model.

## Assumptions and Limitations
*   **Assumptions:** Linearity, independence of observations, and normal distribution of residuals.
*   **Limitations:** Correlation does not imply causation; qualitative factors (management quality) are not captured in this data.

## Screenshots
*   **Simple Regression:** `screenshots/simple_regression_output.png`
*   **Multiple Regression:** `screenshots/multiple_regression_output.png`
*   **Residual Analysis:** `screenshots/residuals_preview.png`
*   **Model Comparison:** `screenshots/model_comparison_preview.png`
