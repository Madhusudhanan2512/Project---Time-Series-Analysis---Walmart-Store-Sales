#  Walmart Time Series Sales Forecasting

This capstone project aims to solve Walmart's inventory management and demand forecasting challenges using time-series analysis and regression modeling. By leveraging historical sales and external variables like temperature, CPI, and unemployment, this project forecasts weekly sales for top-performing stores and evaluates key business insights.

## Video Presentation: Click on this link: https://drive.google.com/file/d/1Ok5vu05VKmtrG3h1lRAOW5BL-fvVH-ku/view?usp=sharing

---

##  Problem Statement

Walmart faces operational inefficiencies due to mismatch between supply and demand. Issues like stockouts and excess inventory affect store performance and customer satisfaction. The project focuses on using **time series forecasting** to improve inventory visibility, reduce stock issues, and enhance overall supply chain efficiency.

---

##  Objectives

- Analyze the relationship between **Weekly Sales** and:
  - Unemployment rate
  - Temperature
  - Consumer Price Index (CPI)
- Forecast sales for the **next 12 weeks** for the top 5 performing stores.

---

##  Dataset Overview

| Column           | Description                         |
|------------------|-------------------------------------|
| Store            | Store number (1–45)                 |
| Date             | Weekly dates                        |
| Weekly Sales     | Target variable                     |
| Holiday Flag     | Whether it was a holiday            |
| Temperature      | Daily temperature                   |
| Fuel Price       | Fuel price on that date             |
| CPI              | Consumer price index                |
| Unemployment     | Unemployment rate                   |

- Total records: **6,435**
- Total stores: **45**
- Target: `Weekly_Sales`

---

##  Data Preprocessing

###  Steps:
- **Data Cleaning**: No missing values, but 481 outliers found in `Unemployment`.
- **Data Transformation**: Log transformation for non-stationary sales data.
- **Data Reduction**: Feature selection based on correlation & stationarity.
- **Encoding**: Performed for time-based modeling.

---

##  Modeling Approach

### Algorithms Used:

1. **FB Prophet**
   - Ideal for time series with seasonal patterns
   - Handles outliers, missing values, and holidays
   - Decomposes series into trend, seasonality, and holidays

2. **Ordinary Least Squares (OLS) Regression**
   - Used for regression between variables like Temperature vs Weekly Sales

---

##  Model Evaluation

###  Metrics:
- **Root Mean Squared Error (RMSE)** used for time-series predictions

| Store     | RMSE ($)     |
|-----------|--------------|
| Store 2   | 63,888.54    |
| Store 4   | 62,167.86    |
| Store 13  | 61,761.98    |
| Store 14  | ~63,000*     |
| Store 20  | 102,392.25   |


---

##  Key Inferences

- **Negative correlation** observed:
  - Sales ↑ when Unemployment ↓
  - Sales ↑ when Temperature ↓
  - Sales ↑ when CPI ↓
- **Store 20** had the highest RMSE due to irregular sales patterns.
- **Store 13** showed consistent and accurate predictions.
- Model trust is high for **Store 2, 4, and 13**.

---

##  Conclusion

- FB Prophet is well-suited for retail time-series forecasting due to seasonality and holiday components.
- Model performance varies by store; some require custom tuning.
- Accurate forecasts improve inventory planning, reduce costs, and enhance customer satisfaction.

---

##  Tech Stack

- Python
- Facebook Prophet
- Statsmodels (for OLS Regression)
- Pandas, NumPy
- Matplotlib, Seaborn
- Jupyter Notebook

---

For feedback or questions, feel free to open an issue or contact the author.
