# 📦 Retail_Sales_Analytics_RFM_Forecasting

## 📌 Project Overview
This project focuses on forecasting product-level demand using historical retail transaction data.  
The goal is to reduce stockouts and support better inventory planning by evaluating multiple time-series forecasting models under real-world retail demand conditions.

---

## 🎯 Objective
- Forecast future daily product demand
- Compare baseline and advanced time-series models
- Analyze limitations of statistical models on intermittent demand
- Provide business-relevant insights for inventory planning

---

## 🧾 Dataset Description
- ~550,000 retail transaction records
- Data aggregated to daily sales per product (SKU)
- Focused on high-volume products for modeling
- Time-based split used (80% train, 20% test)

---

## 🔧 Data Preparation
- Converted invoice timestamps to datetime format
- Aggregated transaction-level data into daily product sales
- Filled missing dates with zero sales
- Sorted data chronologically
- Prepared continuous time series for forecasting models

> Note: This step is feature preparation, not exploratory analysis.

---

## 📊 Forecasting Models Implemented

### Baseline Models
- Naive Forecast
- Moving Average
- Rolling Moving Average

### Advanced Models
- Exponential Smoothing (ETS)
- SARIMA (Seasonal ARIMA)
- SARIMA with log-transformed target (`log1p`)

---

## 🧪 Stationarity & Seasonality
- Stationarity tested using Augmented Dickey-Fuller (ADF) test
- Series found to be stationary (p-value < 0.05)
- Weekly seasonality considered (seasonal period = 7)
- Log transformation applied to stabilize variance and reduce impact of extreme spikes

---

## 📈 Evaluation Metrics
Models were evaluated on the original sales scale using:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

---

## 🏆 Results Summary

| Model | Performance |
|------|------------|
| Naive Forecast | Baseline |
| Moving Average | Moderate improvement |
| Rolling Moving Average | Adaptive but lagging |
| Exponential Smoothing | Underperformed on sparse demand |
| SARIMA | Improved performance |
| **SARIMA (Log-Transformed)** | **Best overall performance** |

---

## 💡 Key Insights
- Training on a 10% subset vs full dataset produced similar results, indicating model stability
- Demand is highly intermittent with sudden spikes
- Statistical models smooth extreme demand values
- Increasing dataset size improves confidence but not predictive behavior

---

## 🧠 Business Interpretation
The final SARIMA model with log transformation provides stable and conservative demand forecasts.  
Due to intermittent demand patterns, forecasts should be complemented with safety stock strategies during peak periods.

---

## 🔮 Future Improvements
- Intermittent demand models (Croston, SBA, TSB)
- Incorporation of external variables (promotions, holidays)
- Hierarchical forecasting (category → product)
- Machine learning models with lag-based features

---

## 🛠️ Tech Stack
- Python
- Pandas, NumPy
- Statsmodels
- Matplotlib
- Jupyter Notebook

---

## 📂 Project Structure
<img width="442" height="530" alt="Screenshot 2026-01-30 220553" src="https://github.com/user-attachments/assets/4e496308-e759-40bd-b1b6-1a2c5deeb455" />


---

## 👤 Author
**Rajdip**

If you found this project useful, feel free to ⭐ the repository.

