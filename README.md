# Predicting Courier Activity for Optimal Operations

##  Project Overview
This project focuses on forecasting the number of online courier partners. By accurately predicting courier activity, Wolt can optimize resource allocation, ensuring the right number of couriers are available to meet customer demand while reducing operational costs.

The primary goal is to **forecast courier demand for a 30-day horizon**.

---

## Setup and Run Instructions

### 1. Environment Configuration
 This project uses a `.env` file to manage sensitive information and API keys, ensuring they are not pushed to GitHub.

1.  **Clone the Repository**:
    ```bash
    git clone https://github.com/edrishakimi1/predicting-courier-activity.git
    cd predicting-courier-activity
    ```



### 2. Running the Notebook
* Open `Wolt_Intern_Assignment_2025.ipynb`.
* **Section B**: Covers Data Insights, Outlier Detection, and Trends.
* **Section C**: Contains the Model implementation and Forecasting.

---

##  Data Insights and Preprocessing (Section B)
Before modeling, the data underwent rigorous cleaning to improve reliability:
* **Outlier Correction**: Initial data contained significant spikes. These were identified and corrected using the **KNN (K-Nearest Neighbors) method**.
* **Growth Trends**: The analysis showed an upward trend in courier demand as Wolt's usage grows.
* **Seasonality**: Demand varies by day of the week, with fewer couriers often needed toward the weekend as people dine out instead of ordering in.



---

##  Evaluation Criteria and Results (Section C)
Two primary models were evaluated using **Rolling Window Cross-Validation** to ensure realistic time-series predictions.

### Model Comparison Table
| Model | $R^2$ Score | Performance Summary |
| :--- | :--- | :--- |
| **Prophet** | **0.832** | Best performance; accurately captured demand trends and seasonality. |
| **XGBoost** | **0.432** | Struggled to capture the broader upward trends in this dataset. |

---

## Conclusion
The **Prophet model** is the recommended solution for this forecasting task.

**Reasoning:**
* **Superior Accuracy**: Prophet achieved a significantly higher $R^2$ (0.832) compared to XGBoost.
* **Trend Handling**: It effectively predicted an average of **72 couriers/day** for the 30-day forecast period.
* **Operational Impact**: These predictions allow Wolt to improve operational efficiency and enhance customer satisfaction by meeting demand effectively.

---

##  Future Recommendations
To further enhance forecasting accuracy, the following steps are proposed:
* **Ensemble Approach**: Combine Prophet for trend detection with XGBoost for short-term fluctuations.
* **External Factors**: Incorporate public holidays, promotions, and local traffic data.
* **Alternative Models**: Explore LSTMs (Deep Learning) or ARIMA/SARIMA for advanced seasonality.
