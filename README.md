# Weather-Based-Power-Load-Forecasting


---

## **Project Workflow (What the Code Does)**

### **1. Data Loading & Cleaning**
- Loads hourly PJME dataset  
- Parses datetime index  
- Handles:
  - Missing values → interpolated  
  - Duplicate timestamps  
  - Outliers (removes top 1% extreme values)

---

### **2. Exploratory Data Analysis (EDA)**  
Includes multiple visualizations:

- Time-series line plots  
- Seasonal decomposition  
- Distribution plots  
- Hourly and weekly consumption patterns  
- Heatmaps  
- Month-wise consumption  
- Weekday vs Weekend analysis  
- Radial (polar) 24-hour energy cycle  
- Seasonal trend shading  

These visualizations reveal **daily, weekly, monthly, and seasonal patterns** in energy usage.

---

### **3. Feature Engineering**
The script generates:

- Hour, day of week  
- Month, quarter, year  
- Day of year, week of year  
- Lag features:
  - `lag_24` → previous day
  - `lag_168` → previous week  

These features help ML models learn temporal dependencies.

---

### **4. Train-Test Split**
- Training: all data before **2018**
- Testing: all data from **2018 onward**

Graphically visualized for clarity.

---

### **5. Machine Learning Models**
The following models are trained:

- **Random Forest Regressor**
- **Gradient Boosting Regressor**
- **XGBoost Regressor**
- **LightGBM Regressor**

Each model is evaluated using:

- MAE  
- RMSE  
- MAPE  

A **comparison table** is generated.

---

### **6. Best ML Model Prediction**
- Automatically selects the best model based on RMSE  
- Plots:
  - Actual vs Predicted  
  - Error histogram  
  - Scatter plot  

---

### **7. Deep Learning Model — LSTM**
Steps:

1. Min-Max scaling  
2. Sequence generation (72-step sequences)  
3. LSTM architecture with dropout  
4. Training + validation loss curves  
5. Performance metrics  

LSTM results are added to the model comparison table.

---

### **8. Final Comparison**
A bar chart compares MAE and RMSE across all models including LSTM.

---

### **9. Week-Level Forecast Example**
Predicts and visualizes energy load for **Jan 1–7, 2018** using the best ML model.

---

## **Best Model Summary**
At the end of execution, the code prints:

- Name of best model  
- MAE  
- RMSE  
- MAPE  

---

