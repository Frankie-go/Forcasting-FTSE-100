# Forcasting-FTSE-100
Try fitting the FTSE index to 2025 using exponential smoothing, ARIMA, and regression forecasting.

## 📖 Project Overview
This project was developed as part of the **MATH6011 Forecasting coursework**.  
The goal is to forecast the behaviour of key UK economic indicators until **December 2025**, and to evaluate whether they can be used to forecast the **FTSE 100 index**.  

The project applies **Exponential Smoothing, ARIMA, and Regression (XGBoost)** methods to real datasets obtained from the **UK Office for National Statistics (ONS)**.

---

## 📊 Data
Four monthly time series from ONS are analysed:

- **K54D**: Average weekly earnings (private sector pay)  
- **EAFV**: Retail sales index (household goods)  
- **K226**: Extraction of crude petroleum and natural gas  
- **JQ2J**: Manufacturing and business sector turnover and orders  

The FTSE 100 index is used as the target variable in regression analysis.

---

## ⚙️ Methods
1. **Exponential Smoothing (Holt-Winters models)**  
   - Forecasted each indicator separately until Dec 2025  
   - Seasonal decomposition and residual diagnostics performed  

2. **ARIMA (SARIMA)**  
   - Applied to K54D series with seasonal + first differencing  
   - Final model: `SARIMA(0,1,2)(0,1,1)[12]`  
   - Compared performance with exponential smoothing  

3. **Regression (XGBoost)**  
   - Used K54D, EAFV, K226, and JQ2J as explanatory variables  
   - Predicted FTSE 100 index until Dec 2025  
   - Performed multicollinearity test (VIF) and feature importance analysis  

---

## 📈 Key Results
- **Exponential Smoothing** achieved strong predictive accuracy on K54D (MAPE ≈ 1.09%).  
- **ARIMA vs Exponential Smoothing**: Exponential smoothing outperformed SARIMA on K54D (MAPE 1.09% vs 1.73%).  
- **Regression (XGBoost)**:  
  - R² = 0.81, MAPE ≈ 6.8%  
  - K54D identified as the most important predictor of FTSE.  

---

## 📂 Repository Structure
