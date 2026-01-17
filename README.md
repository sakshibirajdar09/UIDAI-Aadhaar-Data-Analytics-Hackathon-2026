# 🇮🇳 UIDAI Aadhaar Data Analysis & Service Demand Prediction  
### UIDAI–NIC Data Hackathon 2026 Submission

**Participant:** Sakshi Santosh Birajdar  
**Theme:** Unlocking Societal Trends in Aadhaar Enrolment and Update Services Using Data Analytics and Predictive Modeling

---

## 📌 Introduction

Aadhaar is the foundation of identity verification in India and is essential for accessing government schemes, subsidies, and public services.  
Millions of citizens depend on timely Aadhaar enrolment and update services, yet demand varies widely across districts, months, and age groups.

This project uses **data analytics, visualization, and machine learning** to uncover service demand patterns and predict high-pressure service regions, helping administrators shift from **reactive management to proactive planning**.

---

## 🎯 Problem Statement

UIDAI faces operational challenges such as:

- Uneven distribution of service demand across districts
- Sudden spikes in update requests during certain months
- Overcrowded enrolment centers in urban areas
- Underutilized infrastructure in low-demand regions

Currently, service planning is mostly reactive and based on historical workload.

### Objective

To build a data-driven system that can:

1. Analyze enrolment and update patterns across India  
2. Identify districts facing high service pressure  
3. Detect seasonal and demographic trends  
4. Predict future service demand using machine learning  
5. Support administrative planning through dashboards

---

## 💡 Solution Overview

The solution consists of three integrated components:

### 🔹 Data Engineering Pipeline
- Merging multiple UIDAI datasets
- Cleaning, standardizing, and aggregating records
- Creating analytical features

### 🔹 Analytics & Predictive Modeling
- Exploratory analysis for trends and hotspots
- Regression model for demand forecasting
- Classification model for high-risk districts

### 🔹 Power BI Decision Dashboard
- Interactive state and district filters
- Monthly trend tracking
- Service pressure indicators

Together, these components transform raw UIDAI data into **actionable governance intelligence**.

---

## 📂 Project Folder Structure

UIDAI_AADHAAR_DATA_ANALYSIS_HACKATHON/

├── data/
│ ├── processed/
│ │ ├── biometric_clean.csv
│ │ ├── biometric_full.csv
│ │ ├── demographic_clean.csv
│ │ ├── demographic_full.csv
│ │ ├── enrolment_clean.csv
│ │ ├── enrolment_full.csv
│ │ ├── master_aadhaar_data.csv
│ │ ├── final_aadhaar_dashboard_data.csv
│ │ └── predicted_service_demand.csv
│ └── raw/
│
├── notebooks/
│ ├── 01_merge_datasets.ipynb
│ ├── 02_data_cleaning.ipynb
│ ├── 03_enrolment_analysis.ipynb
│ ├── 04_combined_analysis.ipynb
│ └── 05_service_demand_prediction.ipynb
│
├── outputs/
│ ├── Actual vs Predicted Aadhaar Updates.png
│ ├── High-Risk District Prediction.png
│ ├── age_group_distribution.png
│ ├── age_wise_summary.png
│ ├── districts_service_load.png
│ ├── monthly_trend.png
│ ├── top_states_enrolment.png
│ └── top_states_updates.png
│
├── requirements.txt
├── README.md
└── .gitignore


---

## 🔄 Data Pipeline

### 🟢 Step 1 — Dataset Merging  
Notebook: `01_merge_datasets.ipynb`

Purpose:
- Combine multiple monthly CSV files from UIDAI datasets

Tasks:
- Load all files using `glob`
- Concatenate datasets by service type
- Save merged datasets for cleaning

Outputs:
- `enrolment_full.csv`
- `demographic_full.csv`
- `biometric_full.csv`

---

### 🟢 Step 2 — Data Cleaning & Standardization  
Notebook: `02_data_cleaning.ipynb`

Purpose:
- Improve data quality and consistency

Tasks:
- Remove null and duplicate rows
- Standardize state and district names
- Fix date formats
- Convert age-group columns to numeric
- Create:
  - total_enrol
  - total_demo_updates
  - total_bio_updates

Outputs:
- Clean datasets stored in `/processed`

---

### 🟢 Step 3 — Combined Analysis & Feature Engineering  
Notebook: `04_combined_analysis.ipynb`

Purpose:
- Integrate all service datasets

Tasks:
- Aggregate district-wise monthly totals
- Calculate:
  - total_updates
  - service_ratio (update pressure index)
- Prepare analytical dataset

Outputs:
- `master_aadhaar_data.csv`

---

### 🟢 Step 4 — Final Dashboard Dataset Preparation  
Notebook: `final_cleaning.ipynb` (merged into workflow)

Purpose:
- Final polishing for Power BI

Tasks:
- Remove noise rows
- Standardize inconsistent state names
- Remove zero-activity records

Output:
- `final_aadhaar_dashboard_data.csv`

---

## 📊 Exploratory Data Analysis & Insights

Visual analysis answered key governance questions:

### 🔹 State-wise Enrolment Distribution
Identifies states with consistently high Aadhaar registrations.

### 🔹 State-wise Update Demand
Shows regions where citizens frequently update Aadhaar details.

### 🔹 Monthly Service Trend
Detects seasonal spikes in service demand.

### 🔹 District-Level Service Load
Reveals districts under extreme operational pressure.

### 🔹 Age-wise Enrolment & Update Patterns
Shows demographic groups driving service demand.

All visualizations are saved in: /outputs/


And used both in the report and dashboard validation.

---

## 🤖 Predictive Modeling

Notebook: `05_service_demand_prediction.ipynb`

### 🔵 Model 1 — Service Demand Prediction

Algorithm:
- Linear Regression

Features:
- Month number
- Enrolments
- Demographic updates
- Biometric updates

Target:
- Total updates

Purpose:
- Forecast workload volume for upcoming months

Output:
- Actual vs Predicted scatter plot

---

### 🔵 Model 2 — High-Risk District Classification

Algorithm:
- Random Forest Classifier

High-Risk Definition:
- Districts in top 25% of update-to-enrolment ratio

Features:
- Enrolments
- Update counts
- Seasonal indicator

Purpose:
- Early detection of service overload zones

Outputs:
- Confusion matrix visualization
- High-risk labels in dataset

Saved as:
- `predicted_service_demand.csv`

---

## 📊 Power BI Interactive Dashboard

Dataset Used:
- `final_aadhaar_dashboard_data.csv`

### Dashboard Capabilities

#### 🔹 State & District Filters
Allows drill-down into local service demand patterns.

#### 🔹 Monthly Trend Charts
Helps identify peak workload periods.

#### 🔹 Service Pressure Index
Visualizes districts operating beyond optimal capacity.

#### 🔹 Age Group Analysis
Identifies which population segments generate higher updates.

---

### Decision Support Value

The dashboard supports:

- Infrastructure expansion planning
- Mobile enrolment unit deployment
- Staffing optimization
- Policy-driven awareness campaigns

It functions as a **real-time analytical decision support system** for administrators.

---

## 🌍 Social & Administrative Impact

This project enables UIDAI to:

- Reduce citizen waiting times
- Improve service availability
- Optimize resource utilization
- Prevent infrastructure overload

By introducing predictive planning, Aadhaar services become more **efficient, equitable, and resilient**.

---

## ▶️ How to Run the Project

### Install Requirements

```bash
pip install -r requirements.txt
```
### Run Notebooks in Order
```bash
01_merge_datasets.ipynb

02_data_cleaning.ipynb

04_combined_analysis.ipynb

05_service_demand_prediction.ipynb
```
### Power BI
```bash
Open Power BI Desktop

Load final_aadhaar_dashboard_data.csv

Refresh visuals
```

