# Residual Analysis

As part of validating our multiple linear regression model, we analyzed the residuals (the difference between the **Actual Sales** and the **Predicted Sales**) to identify outliers and understand where our model's predictions deviate the most.

##  Top 5 Largest Positive Residuals
*A positive residual means the store's ACTUAL sales were much HIGHER than what the model predicted.*

| Observation (Store Row) | Predicted Sales | Actual Sales | Residual (Actual - Predicted) |
| :--- | :--- | :--- | :--- |
| 230 | $760,190.33 | $870,937.40 | +$110,747.07 |
| 112 | $610,240.57 | $713,611.16 | +$103,370.59 |
| 291 | $721,103.34 | $813,316.71 | +$92,213.37 |
| 202 | $699,122.19 | $787,715.51 | +$88,593.32 |
| 118 | $732,423.88 | $820,519.04 | +$88,095.16 |

##  Top 5 Largest Negative Residuals
*A negative residual means the store's ACTUAL sales were much LOWER than what the model predicted.*

| Observation (Store Row) | Predicted Sales | Actual Sales | Residual (Actual - Predicted) |
| :--- | :--- | :--- | :--- |
| 90 | $761,312.91 | $627,171.90 | -$134,141.01 |
| 67 | $801,235.49 | $685,379.08 | -$115,856.41 |
| 45 | $704,213.88 | $595,467.60 | -$108,746.28 |
| 26 | $904,776.56 | $800,451.94 | -$104,324.62 |
| 237 | $802,471.56 | $721,079.35 | -$81,392.21 |

---

##  Business Interpretation of Residuals

### What These Residuals Mean in Business Terms
Residuals represent the "unexplained variance" in our model. 
* **Large Positive Residuals (Over-performers):** These specific stores are generating significantly more revenue than their footfall, marketing, and inventory metrics suggest they should. In business terms, this usually indicates the presence of "hidden" positive factors not captured in our dataset. This could be an exceptionally talented store manager, highly skilled sales staff driving larger basket sizes, or a localized community event driving unrecorded high-intent buyers.
* **Large Negative Residuals (Under-performers):** These stores have all the right inputs (good footfall, high marketing spend, good inventory) but are failing to convert them into expected sales. This points to hidden operational bottlenecks. Potential causes include poor localized management, disruptive nearby construction blocking store access, poor visual merchandising, or stock-outs of highly desired specific items (even if general inventory availability % is high).

### Model Over-Prediction vs. Under-Prediction
By observing the pattern of residuals, we can identify systemic biases in our model:
* **Under-Predicting:** If we group our residuals and notice that certain store types (like Airport stores or High Street locations in the West) consistently show positive residuals, it means the model is **under-predicting** their success. This implies that the baseline premium of being in an Airport location is stronger than our dummy variables captured, likely due to captive-audience impulse buying.
* **Over-Predicting:** Conversely, if specific regions heavily populate the negative residuals list, the model is **over-predicting** their revenue. This suggests there are macro-economic headwinds, stronger localized competition, or supply chain issues in that specific region that our current data variables are failing to account for.
