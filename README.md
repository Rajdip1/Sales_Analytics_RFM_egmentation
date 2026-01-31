# 📦 Retail Sales Analytics – RFM Segmentation & Demand Forecasting

## 📌 Project Overview
This project is an end-to-end **retail sales analytics** solution that combines **customer segmentation using RFM analysis** with **product-level demand forecasting** based on historical retail transaction data.

The objective is to help businesses **understand customer value**, **anticipate future demand**, and **support inventory planning decisions** under real-world retail conditions.

---

## 🎯 Project Objectives
- Segment customers using **Recency, Frequency, and Monetary (RFM) analysis**
- Forecast future daily product demand
- Compare baseline and advanced **time-series forecasting models**
- Analyze the limitations of statistical models on **intermittent demand**
- Translate analytical results into **business-relevant insights**

---

## 🧾 Dataset Description
- ~550,000 retail transaction records
- Customer-level and product-level purchase data
- Aggregated to **daily sales per product (SKU)**
- Focused on high-volume products for modeling
- Time-based split used:
  - **80% training**
  - **20% testing**

---

## 🔧 Data Preparation
- Converted invoice timestamps to datetime format
- Aggregated transaction-level data into daily product sales
- Filled missing dates with zero sales to maintain continuity
- Sorted records chronologically
- Prepared clean, continuous time series for forecasting models

> ⚠️ *Note:* These steps focus on feature preparation, not exploratory data analysis.

---

## 👥 Customer Segmentation (RFM Analysis)
- Calculated **Recency**, **Frequency**, and **Monetary** values per customer
- Assigned **quantile-based RFM scores (1–5)**
- Combined scores to form an overall customer value metric
- Segmented customers into actionable business groups such as:
  - Champions
  - Loyal Customers
  - Big Spenders
  - At-Risk Customers
  - Lost Customers
- Applied log transformation to handle skewed distributions

---

## 📊 Forecasting Models Implemented

### 🔹 Baseline Models
- Naive Forecast
- Moving Average
- Rolling Moving Average

### 🔹 Advanced Models
- Exponential Smoothing (ETS)
- SARIMA (Seasonal ARIMA)
- SARIMA with log-transformed target (`log1p`)

---

## 🧪 Stationarity & Seasonality
- Stationarity tested using the **Augmented Dickey-Fuller (ADF) test**
- Time series found to be stationary (**p-value < 0.05**)
- Weekly seasonality incorporated (**seasonal period = 7**)
- Log transformation applied to:
  - Stabilize variance
  - Reduce the impact of extreme demand spikes

---

## 📈 Evaluation Metrics
All models were evaluated on the **original sales scale** using:
- **Mean Absolute Error (MAE)**
- **Root Mean Squared Error (RMSE)**

---

## 🏆 Results Summary

| Model | Performance |
|------|------------|
| Naive Forecast | Baseline |
| Moving Average | Moderate improvement |
| Rolling Moving Average | Adaptive but lagging |
| Exponential Smoothing | Underperformed on sparse demand |
| SARIMA | Improved performance |
| **SARIMA (Log-Transformed)** | ⭐ **Best overall performance** |

---

## 💡 Key Insights
- Training on a 10% subset vs. the full dataset produced similar results, indicating model stability
- Demand patterns are **highly intermittent with sudden spikes**
- Statistical models tend to smooth extreme values
- Increasing dataset size improves confidence but not predictive behavior

---

## 🧠 Business Interpretation
The **log-transformed SARIMA model** provides stable and conservative demand forecasts.  
Given the intermittent nature of demand, forecasts should be complemented with **safety stock strategies**, especially during peak sales periods.

---

## 🔮 Future Improvements
- Intermittent demand forecasting models (Croston, SBA, TSB)
- Inclusion of external variables (promotions, holidays, events)
- Hierarchical forecasting (category → subcategory → product)
- Machine learning models with lag-based and rolling features

---

## 🛠️ Tech Stack
- Python 
- Pandas, NumPy
- Statsmodels
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## 📂 Project Structure
<img width="511" height="643" alt="Screenshot 2026-01-31 215541" src="https://github.com/user-attachments/assets/cc5d14d8-2616-4f7a-8e4c-c8088f3da9b4" />

---

## 👤 Author
**Rajdip**

If you found this project useful, feel free to ⭐star the repository.
