# Model Comparison Report

This report compares the performance, insights, explanatory power, and structural limitations of our simple linear regression models against our consolidated multiple linear regression model.

##  Summary Comparison Table

| Required Item | Simple Regression (Footfall) | Simple Regression (Marketing) | Multiple Regression Model |
| :--- | :--- | :--- | :--- |
| **Model Name** | Simple Linear Regression - Traffic Impact | Simple Linear Regression - Ad Spend Impact | Multiple Linear Regression - Holistic Store Performance |
| **Variables Used** | **Y:** `monthly_sales`<br>**X:** `footfall` | **Y:** `monthly_sales`<br>**X:** `marketing_spend` | **Y:** `monthly_sales`<br>**X:** `Is_East`, `Is_South`, `Is_West`, `Is_High_Street`, `Is_Airport`, `marketing_spend`, `footfall`, `avg_discount_pct`, `staff_count`, `inventory_availability_pct`, `competitor_distance_km`, `holiday_flag`, `customer_rating` |
| **R-squared** | **73.27%** (High single-variable fit) | **16.72%** (Low standalone explanatory power) | **84.34%** (Highest predictive and operational explanatory power) |
| **Significant Variables** | `footfall` ($p < 0.001$) | `marketing_spend` ($p < 0.001$) | `marketing_spend`, `footfall`, `staff_count`, `inventory_availability_pct`, `competitor_distance_km`, `holiday_flag`, `customer_rating` (All $p < 0.05$) |
| **Business Usefulness** | **High (Tactical):** Directly validates store capacity, layout planning, and structural site selection parameters. | **Low to Moderate:** Proves positive ad returns but cannot reliably forecast overall revenue on its own. | **Very High (Strategic):** Provides a comprehensive decision-making roadmap for inventory control, regional staffing, marketing budget distribution, and seasonal scaling. |
| **Limitations** | **Omitted Variable Bias:** Ignores product stock, operational service quality, marketing ads, and competitor presence. | **High Residual Variance:** Ignores physical presence, localized store operations, and geographic location constraints. | **Contextual Limits:** Does not capture sudden localized macro-economic swings, shifts in vendor relationships, or brand-level shifts. |

---

##  In-Depth Model Breakdown

### 1. Explanatory Power ($R^2$) & Operational Alignment
* **Simple Footfall Model ($R^2 = 73.27\%$):** Demonstrates that foot traffic alone is a primary foundation of store sales performance. However, relying on this entirely over-simplifies operations.
* **Simple Marketing Model ($R^2 = 16.72\%$):** Indicates that while marketing spending significantly moves the needle ($p < 0.05$), its low $R^2$ confirms that ad spending is a supporting lever rather than an independent driver of retail revenue.
* **Multiple Regression Model ($R^2 = 84.34\%$):** Combining our fields increases explanatory power significantly, capturing an extra $11.07\%$ of store performance variations compared to traffic alone. This shows that the interaction of operational indicators yields a far clearer corporate insight.

### 2. Business Decision-Making Impact
* **The Simple Models** are useful for standalone department choices (e.g., assessing real estate foot traffic or evaluating base ad returns).
* **The Multiple Model** acts as an integrated executive toolkit. It highlights that an optimal store strategy shouldn't just chase footfall—it requires protecting shelf stock (`inventory_availability_pct`), adjusting for local rivals (`competitor_distance_km`), and ensuring store floors are adequately supported (`staff_count`).

### 3. Statistically Weak Metrics & Interpretive Caution
In our final multiple regression configuration:
* `avg_discount_pct` ($p = 0.175$), `Is_East` ($p = 0.096$), `Is_South` ($p = 0.230$), and `Is_High_Street` ($p = 0.224$) exhibit weak structural significance ($p > 0.05$). 
* **Business Takeaway:** Managers should avoid cutting product prices aggressively via broad discounting under the assumption that it linearly improves store revenue, as its variance is too wide to be predictive.
