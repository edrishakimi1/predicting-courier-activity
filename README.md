# Predicting Courier Activity for Optimal Operations

##  Project Overview
[cite_start]This project focuses on forecasting the number of online courier partners[cite: 1, 2]. [cite_start]By accurately predicting courier activity, Wolt can optimize resource allocation, ensuring the right number of couriers are available to meet customer demand while reducing operational costs[cite: 13, 170].

[cite_start]The primary goal is to **forecast courier demand for a 30-day horizon**[cite: 13].

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
* [cite_start]**Section B**: Covers Data Insights, Outlier Detection, and Trends[cite: 11].
* [cite_start]**Section C**: Contains the Model implementation and Forecasting[cite: 13, 59, 106].

---

##  Data Insights and Preprocessing (Section B)
[cite_start]Before modeling, the data underwent rigorous cleaning to improve reliability[cite: 15]:
* [cite_start]**Outlier Correction**: Initial data contained significant spikes[cite: 29]. [cite_start]These were identified and corrected using the **KNN (K-Nearest Neighbors) method**[cite: 15, 33].
* [cite_start]**Growth Trends**: The analysis showed an upward trend in courier demand as Wolt's usage grows[cite: 14, 107].
* [cite_start]**Seasonality**: Demand varies by day of the week, with fewer couriers often needed toward the weekend as people dine out instead of ordering in[cite: 108, 109].



---

##  Evaluation Criteria and Results (Section C)
[cite_start]Two primary models were evaluated using **Rolling Window Cross-Validation** to ensure realistic time-series predictions[cite: 70, 81].

### Model Comparison Table
| Model | $R^2$ Score | Performance Summary |
| :--- | :--- | :--- |
| **Prophet** | **0.832** | [cite_start]Best performance; accurately captured demand trends and seasonality[cite: 16, 156]. |
| **XGBoost** | **0.432** | [cite_start]Struggled to capture the broader upward trends in this dataset[cite: 16, 156]. |

---

## Conclusion
[cite_start]The **Prophet model** is the recommended solution for this forecasting task[cite: 156, 177].

**Reasoning:**
* [cite_start]**Superior Accuracy**: Prophet achieved a significantly higher $R^2$ (0.832) compared to XGBoost[cite: 156].
* [cite_start]**Trend Handling**: It effectively predicted an average of **72 couriers/day** for the 30-day forecast period[cite: 17, 164].
* [cite_start]**Operational Impact**: These predictions allow Wolt to improve operational efficiency and enhance customer satisfaction by meeting demand effectively[cite: 170, 171].

---

##  Future Recommendations
[cite_start]To further enhance forecasting accuracy, the following steps are proposed[cite: 190]:
* **Ensemble Approach**: Combine Prophet for trend detection with XGBoost for short-term fluctuations.
* **External Factors**: Incorporate public holidays, promotions, and local traffic data.
* **Alternative Models**: Explore LSTMs (Deep Learning) or ARIMA/SARIMA for advanced seasonality.