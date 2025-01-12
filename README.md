# Revenue-Modelling

Revenue forecast model using the 'Prophet' package in R.

---

## 📊 Data Generation Methodology

The dataset used for this sample model was generated with the help of LLM, based on the following criteria:

- **Baseline patient visits** that fluctuated around **900 to 1,200 visits per month**.
- **Seasonal adjustments** to reflect higher visits in certain months (e.g., **flu season** in fall/winter) and lower visits in summer (when elective procedures are typically down).
- **Random noise** to introduce variability.

The **payer mix (Private, Medicare, Medicaid)** was randomized, and the final percentages were normalized to sum to **100%** for each month.

Different **reimbursement rates** were assumed for each payer type:

| **Payer Type** | **Reimbursement Rate (Range)** |
|---------------|---------------------------------|
| Private       | $150 to $180 per patient        |
| Medicare      | $120 to $140 per patient        |
| Medicaid      | $90 to $110 per patient         |

The **monthly revenue per payer type** was calculated using the following formula:

\[
\text{Revenue} = \text{Patient Visits} \times \text{Payer Mix} \times \text{Reimbursement Rate} \times (1 - \text{Denial Rate})
\]

---

## 📋 Columns in the Dataset

- **Date**: Monthly date intervals from **January 2022 to December 2024**.
- **Patient_Visits**: The number of patient visits per month.
- **Private_Revenue**: Revenue generated from private insurance.
- **Medicare_Revenue**: Revenue generated from Medicare.
- **Medicaid_Revenue**: Revenue generated from Medicaid.
- **Claims_Denial_Rate**: Percentage of denied claims each month.
- **Total_Revenue**: The total monthly revenue from all payer sources.

---

## 📈 Key Steps in the R Markdown File

1. **Data Loading**: The dataset was read from `DATA_Revenuemodel.csv`.
2. **Prophet Model**: A revenue forecast was built using the **Prophet package**.
3. **Forecast Visualization**: Historical revenue (2022-2024) and forecasted revenue for **2025** were plotted, including **confidence intervals**.
4. **Table Output**: Forecasted revenue values for each month of **2025** were displayed.

---

## 📊 Forecast Insights

The forecasted revenue for **2025** shows a continuation of the **historical trends** observed from **2022 to 2024**. The model accounts for **seasonality** and **quarterly trends**.

---

## 🔬 Future Techniques to Practice with This Data

In addition to the **Prophet model**, here are three additional techniques that will be practiced with this dataset:

1. **ARIMA (AutoRegressive Integrated Moving Average)**: A traditional time series forecasting method that is effective for stationary data.
2. **ETS (Error, Trend, Seasonality)**: An exponential smoothing technique for time series forecasting.
3. **Random Forest for Time Series**: Using machine learning algorithms to capture non-linear patterns in the data.

---

This project serves as a foundation for exploring advanced time series forecasting techniques to improve **data-driven decision-making**.

