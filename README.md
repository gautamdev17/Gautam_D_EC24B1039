# ⚡ Electricity Bill Prediction using Machine Learning

This project predicts **monthly electricity bills** using machine learning models trained on residential appliance and usage data. We tried out multiple ML algorithms and ended up with a near-perfect prediction using **Random Forest Regressor**.

---

## 📊 Model Performance (R² Score)

| Model               | R² Score             |
|--------------------|----------------------|
| ✅ Random Forest    | **0.9999755665317055** |
| Decision Tree      | 0.9999118343410605   |
| Linear Regression  | 0.9956378681437017   |

---

## 📁 Dataset Description

The dataset includes appliance usage and electricity tariff info:

| Feature         | Description                                             |
|----------------|---------------------------------------------------------|
| `Fan`            | Number of fans                                          |
| `Refrigerator`   | Number of refrigerators                                 |
| `AirConditioner` | Number of air conditioners                              |
| `Television`     | Number of TVs                                           |
| `Monitor`        | Number of monitors                                      |
| `MotorPump`      | Number of motor pumps                                   |
| `MonthlyHours`   | Total monthly hours appliances were used               |
| `TariffRate`     | Rate per unit of electricity (₹ per kWh)               |
| `City`           | Location (label encoded)                               |
| `Company`        | Electricity board name (label encoded)                 |
| `Month`          | Month of usage                                          |
| `ElectricityBill`| Ground truth bill amount in ₹ for the month           |

---

## ✨ Feature Engineering

We created new features to help models learn better relationships.

### 🔧 Custom Features

- `totalAppliances`: total number of appliances in the house  
  ```python
  df["totalAppliances"] = df[['Fan', 'Refrigerator', 'AirConditioner', 'Television', 'Monitor', 'MotorPump']].sum(axis=1)
