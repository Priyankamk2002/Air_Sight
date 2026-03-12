# 🌫️ AirSight — Next Day Air Quality Index (AQI) Predictor

![Python](https://img.shields.io/badge/Python-3.13-blue)
![ML](https://img.shields.io/badge/Machine%20Learning-RandomForest-green)
![Streamlit](https://img.shields.io/badge/Deployed-Streamlit-red)
![Data](https://img.shields.io/badge/Data-EPA%20AirData%202024-orange)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 📌 Project Title
**AirSight — Predicting Next-Day Air Quality Index (AQI) Using Machine Learning**

---

## 📋 Problem Statement

Air pollution is one of the most serious public health threats of the
21st century. The current AQI system only tells people what the air
quality **WAS** — not what it **WILL BE.**

AQI is reported at the end of the day, after people have already been
exposed to pollution. This means:

- 👶 Children breathe toxic air at school before any warning is issued
- 🏥 Hospitals get overwhelmed with patients without advance notice
- 🏫 Schools cannot cancel outdoor events in time
- 🏛️ Governments can only react — not prevent exposure

> **There is no widely accessible system that predicts next-day AQI
> at county level across the United States.**

---

## ✅ Solution

**AirSight** is an end-to-end Machine Learning system that predicts
tomorrow's Air Quality Index using historical AQI patterns, time-based
features, and pollutant information — giving everyone a **24-hour
advance warning** to protect their health.

---

## 🎯 Project Objectives

| Task | Type | Description |
|---|---|---|
| Task 1 | Regression | Predict exact AQI value for next day |
| Task 2 | Classification | Predict AQI health category for next day |

---

## 📦 Dataset

| Property | Details |
|---|---|
| Source | U.S. EPA AirData (Official Government Data) |
| Link | https://aqs.epa.gov/aqsweb/airdata/daily_aqi_by_county_2024.zip |
| Coverage | Full Year 2024 — All 50 US States |
| Granularity | County Level (3,000+ counties) |
| Records | 3,21,695 rows after cleaning |
| License | Public Domain — Free to use |

---

## 🗂️ Project Structure

```
📁 AirSight/
│
├── 📄 app.py                   → Streamlit Web App
├── 📄 airsight.ipynb           → Main Jupyter Notebook
├── 📄 requirements.txt         → Required Libraries
├── 📄 README.md                → Project Documentation
│
└── 📁 models/
     ├── best_regression_model.pkl      → Saved Regression Model
     ├── best_classification_model.pkl  → Saved Classification Model
     └── preprocessor.pkl               → Saved Column Transformer
```

---

## 🔄 Project Workflow

```
Step 1  →  Data Collection       (EPA AirData 2024)
Step 2  →  Data Cleaning         (Handle nulls, outliers, types)
Step 3  →  EDA                   (Visual analysis & insights)
Step 4  →  Feature Engineering   (Lag, Rolling, Time features)
Step 5  →  Train Test Split      (80% train / 20% test)
Step 6  →  Column Transformer    (StandardScaler + OrdinalEncoder)
Step 7  →  Model Building        (Linear, Logistic, Random Forest)
Step 8  →  Model Evaluation      (RMSE, MAE, R², Accuracy, F1)
Step 9  →  Hyperparameter Tuning (class_weight, max_depth)
Step 10 →  Save Best Model       (joblib)
Step 11 →  Streamlit Deployment  (Web App)
```

---

## 🔧 Features Used

| Feature | Description |
|---|---|
| AQI_lag1 | Yesterday's AQI |
| AQI_lag2 | 2 days ago AQI |
| AQI_lag3 | 3 days ago AQI |
| AQI_lag7 | 1 week ago AQI |
| AQI_rolling_mean_3 | 3-day rolling average |
| AQI_rolling_mean_7 | 7-day rolling average |
| AQI_rolling_std_7 | 7-day rolling std deviation |
| Month | Month of year (1-12) |
| Season | Winter / Spring / Summer / Fall |
| Day_of_Week | Monday to Sunday |
| Quarter | Q1 to Q4 |
| Is_Weekend | Weekday or Weekend |
| State_Name | US State |
| County_Name | US County |
| Defining_Parameter | Dominant pollutant (PM2.5, Ozone etc.) |

---

## 🤖 Models & Results

### Regression (Predict AQI Value)
| Model | RMSE | MAE | R² |
|---|---|---|---|
| Linear Regression | 12.63 | 8.57 | 0.5579 |
| Random Forest | 12.38 | 8.40 | 0.5755 |
| **RF Tuned (Best)** | **11.96** | - | **0.6037** |

### Classification (Predict AQI Category)
| Model | Accuracy | F1 Score |
|---|---|---|
| Logistic Regression | 0.82 | 0.81 |
| Random Forest | 0.83 | 0.82 |
| **RF Tuned Balanced (Best)** | **0.79** | **0.80** |

---

## 🎨 AQI Scale Reference

| AQI Range | Category | Color |
|---|---|---|
| 0 - 50 | Good | 🟢 Green |
| 51 - 100 | Moderate | 🟡 Yellow |
| 101 - 150 | Unhealthy for Sensitive Groups | 🟠 Orange |
| 151 - 200 | Unhealthy | 🔴 Red |
| 201 - 300 | Very Unhealthy | 🟣 Purple |
| 301 - 500 | Hazardous | 🟤 Brown |

---

## 🌍 Real World Impact

| Stakeholder | Benefit |
|---|---|
| 👨‍👩‍👧 General Public | Plan outdoor activities in advance |
| 🏥 Hospitals | Prepare staff before patient surges |
| 🏫 Schools | Cancel outdoor events the night before |
| 🏛️ Government | Issue preventive health advisories |
| 🏭 Industries | Reduce emissions on predicted bad days |
| 🔬 Researchers | Benchmark county-level AQI forecasting |

---

## 🚀 How to Run Locally

### 1. Clone Repository
```bash
git clone https://github.com/yourusername/AirSight.git
cd AirSight
```

### 2. Install Requirements
```bash
pip install -r requirements.txt
```

### 3. Run Streamlit App
```bash
streamlit run app.py
```

### 4. Open in Browser
```
http://localhost:8501
```

---

## 📚 Requirements

```
streamlit
pandas
numpy
scikit-learn
joblib
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.13 | Programming Language |
| Pandas | Data Manipulation |
| NumPy | Numerical Computing |
| Scikit-learn | Machine Learning |
| Matplotlib / Seaborn | Data Visualization |
| Joblib | Model Saving |
| Streamlit | Web App Deployment |
| VS Code | Development Environment |
| GitHub | Version Control |

---

## 👨‍💻 Author

**Priyanka MK**
- LinkedIn : [https://linkedin.com/in/yourprofile](https://www.linkedin.com/in/priyanka-mk-/?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3Bt233oH8YTFqdQd3xLbbQ5A%3D%3D)

---

## 📄 License

This project is licensed under the MIT License.

---

## ⭐ If you found this project helpful please give it a Star!
# Air_Sight
