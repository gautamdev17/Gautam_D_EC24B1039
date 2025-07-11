# ⚡ Electricity Bill Prediction using Machine Learning

This project is part of the **MachineHack - Electricity Cost Prediction Challenge**. The goal is to build a machine learning model that accurately predicts monthly electricity bills based on appliance usage, location, company, and tariff rates.

---

## 📁 Dataset Overview

The dataset consists of the following features:

| Feature          | Description |
|------------------|-------------|
| `Fan`            | Number of fans in the residence |
| `Refrigerator`   | Number of refrigerators |
| `AirConditioner` | Number of air conditioners |
| `Television`     | Number of televisions |
| `Monitor`        | Number of monitors or computers |
| `MotorPump`      | Number of motor pumps used |
| `Month`          | The month (1-12) for which electricity is being measured |
| `City`           | The city where the household is located |
| `Company`        | The electricity provider |
| `MonthlyHours`   | Total usage hours of all appliances in that month |
| `TariffRate`     | Cost per unit hour of electricity |
| `ElectricityBill`| (Target) The actual electricity bill in currency units |

---

## 🧠 Models Used

We experimented with multiple models:

- 📈 **Linear Regression**
- 🌳 **Decision Tree Regressor**
- 🌲 **Random Forest Regressor** ✅ *(Best performer)*
- 🚀 **XGBoost Regressor** *(optional, if allowed)*

---

## 🔬 Feature Engineering

We created two additional features:

- `Total_Appliances`: Sum of all appliances used  
- `Usage_Intensity`: `MonthlyHours × TariffRate` (approximate cost factor)

---

## ✅ Final Model: Random Forest Regressor

**Why Random Forest?**  
It’s an ensemble of decision trees that automatically captures interactions like `Fan × TariffRate`, handles non-linearities, and is very robust without requiring deep feature tuning.

**Results on validation set:**

- ✅ **R² Score**: `0.99999945`
- 📉 **RMSE**: Very low — near-zero prediction error.

This level of performance indicates the model is **highly accurate** in predicting electricity costs.

---

## 📊 Visualization

![Scatter Plot](assets/scatter_plot.png)  
*Plot of Predicted vs Actual Bill Values*

---

## 📂 Files

- `electricity_bill_dataset.csv` – Main dataset
- `notebook.ipynb` – Code and model training
- `my_submission.csv` – Final predictions for submission
- `README.md` – This documentation

---

## 🚀 How to Run

1. Clone the repository  
2. Install dependencies:  
   ```bash
   pip install -r requirements.txt
