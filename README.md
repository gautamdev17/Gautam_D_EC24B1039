# 🔌 Electricity Bill Prediction using Random Forest

This project predicts the monthly **Electricity Bill** of residential users using machine learning.  
The dataset contains appliance counts, usage hours, tariff rates, and city/company info.

We use a **Random Forest Regressor** to train the model and apply feature engineering to improve accuracy.

---

## 🚀 Project Highlights

- 📊 Model used: `RandomForestRegressor`
- 🧠 R² Score: **0.99997**
- 🔧 Feature Engineering applied
- 📈 Graphs and heatmaps for analysis

---

## 📁 Dataset Overview

The dataset contains:

| Feature         | Description                                            |
|----------------|--------------------------------------------------------|
| Fan            | Number of fans                                         |
| Refrigerator   | Number of refrigerators                                |
| AirConditioner | Number of air conditioners                             |
| Television     | Number of TVs                                          |
| Monitor        | Number of monitors                                     |
| MotorPump      | Number of motor pumps                                  |
| MonthlyHours   | Appliance usage hours per month                        |
| TariffRate     | Electricity rate per unit (kWh)                        |
| City           | City name (label encoded)                              |
| Company        | Electricity board (label encoded)                      |
| Month          | Month of the year                                      |
| ElectricityBill| The actual electricity cost for the month              |

---

## 🧠 Feature Engineering

Feature engineering means creating **new useful features** from the existing ones to help the model learn better.

### ✨ Custom Features Added

- `totalAppliances`:  
  Total number of appliances in the house  
  ```python
  df["totalAppliances"] = df[['Fan', 'Refrigerator', 'AirConditioner', 'Television', 'Monitor', 'MotorPump']].sum(axis=1)
