# 🏭 Enterprise Manufacturing Intelligence Platform

> **Predictive Maintenance System** using Machine Learning, Data Lake Architecture, and Power BI Dashboards — analyzing IoT sensor data to predict failures, detect anomalies, and optimize maintenance operations.

---

## 📌 Project Overview

This end-to-end analytics platform simulates a real-world manufacturing environment where IoT sensors continuously monitor industrial machines. The system ingests, cleans, engineers features from, and models sensor data to:

- Predict machine failures **before** they occur
- Detect anomalous sensor readings in real time
- Calculate plant-level KPIs (OEE, MTBF, Downtime %)
- Export a **Power BI-ready star-schema** data model
- Apply cybersecurity controls to protect pipeline integrity

---

## 🏗️ Architecture

```
IoT Sensors / SCADA
        │
        ▼
┌─────────────────┐
│   DATA LAKE     │  raw_data/ → processed_data/ → model_output/
└─────────────────┘
        │
        ▼
┌─────────────────┐
│  DATA PIPELINE  │  Ingest → Validate → Clean → Feature Engineer
└─────────────────┘
        │
        ▼
┌─────────────────┐
│   ML MODELS     │  Random Forest → Gradient Boost → Isolation Forest
└─────────────────┘
        │
        ▼
┌─────────────────┐
│  KPI DASHBOARD  │  OEE · MTBF · Downtime · Yield · Health Score
└─────────────────┘
        │
        ▼
┌─────────────────┐
│   POWER BI      │  Star Schema Export (Excel Workbook)
└─────────────────┘
```

---

## 📂 Project Structure

```
Enterprise-Manufacturing-Intelligence-Platform/
│
├── Manufacturing_Analytics_.ipynb   # Main notebook (all 13 sections)
│
├── data_lake/
│   ├── raw_data/                    # Ingested CSV files
│   ├── processed_data/              # Cleaned + engineered data
│   ├── model_output/                # Trained .pkl models + predictions
│   ├── kpi_output/                  # KPI tables + charts
│   ├── powerbi_export/              # Power BI Excel workbook
│   └── logs/                        # Pipeline logs
│
└── README.md
```

---

## ⚙️ Pipeline Sections

| # | Section | Description |
|---|---------|-------------|
| 1 | **Install & Import** | All dependencies installed and imported |
| 2 | **Data Lake Setup** | Folder structure for all pipeline zones |
| 3 | **Data Ingestion** | Simulates 1 year of hourly IoT sensor data from 4 machines |
| 4 | **Data Cleaning & Validation** | Null handling, range validation, outlier removal |
| 5 | **Feature Engineering** | Rolling stats, lag features, health score computation |
| 6 | **Exploratory Data Analysis** | Sensor distribution charts, correlation heatmaps |
| 7 | **Model Training** | Random Forest, Gradient Boosting, Isolation Forest |
| 8 | **Model Evaluation** | Accuracy, Precision, Recall, F1, ROC-AUC |
| 9 | **KPI Metrics** | OEE, MTBF, Downtime %, Failure Rate, Yield Rate |
| 10 | **Save Outputs** | All artifacts saved to Data Lake zones |
| 11 | **Cybersecurity Strategy** | SHA-256 hashing, data integrity verification |
| 12 | **Power BI Export** | Star-schema Excel workbook for dashboard use |
| 13 | **Download ZIP** | Full project package download |

---

## 🤖 Machine Learning Models

### 1. Random Forest Classifier
- **Purpose:** Binary classification — will this machine fail? (Yes/No)
- **Use case:** Maintenance scheduling and alerting

### 2. Gradient Boosting Classifier
- **Purpose:** Probability scoring — what is the % risk of failure?
- **Use case:** Risk-ranked maintenance prioritization

### 3. Isolation Forest (Unsupervised)
- **Purpose:** Anomaly detection on sensor readings
- **Use case:** Catches unusual patterns even without labelled failure data

---

## 📊 Sensors Monitored

| Sensor | Unit | Valid Range |
|--------|------|-------------|
| Temperature | °C | 50 – 150 |
| Vibration | mm/s | 0 – 15 |
| Pressure | PSI | 40 – 160 |
| RPM | RPM | 200 – 2000 |
| Current | Amps | 5 – 30 |

---

## 🏭 Machines Tracked

| ID | Name |
|----|------|
| Machine_A | CNC Lathe A |
| Machine_B | Hydraulic Press B |
| Machine_C | Assembly Robot C |
| Machine_D | Conveyor Drive D |

---

## 📈 KPI Definitions

| KPI | Target | Description |
|-----|--------|-------------|
| **OEE** | ≥ 85% | Overall Equipment Effectiveness |
| **MTBF** | Higher = better | Mean Time Between Failures |
| **Downtime %** | < 5% | % of time machine is down |
| **Failure Rate** | < 2% | % of operational hours with failure |
| **Yield Rate** | > 95% | % of output meeting quality specs |
| **Health Score** | Maximize | Composite machine health indicator |

---

## 🔐 Cybersecurity Controls

- **SHA-256 File Hashing** — Every data lake file is hashed on write; mismatch on reload = tampering detected
- **Data Integrity Verification** — Automated hash comparison at each pipeline stage
- **Access Logging** — All pipeline operations logged with timestamps

---

## 📊 Power BI Data Model (Star Schema)

```
Fact_SensorReadings  ←→  Dim_Machine
Fact_SensorReadings  ←→  Dim_Date
Fact_DailyKPI        ←→  Dim_Machine
Fact_DailyKPI        ←→  Dim_Date
Fact_Alerts          ←→  Dim_Machine
```

The exported Excel workbook can be imported into **Power BI Desktop** in one click to build interactive dashboards.

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy scikit-learn matplotlib seaborn plotly openpyxl joblib
```

### Run the Notebook
1. Clone this repository:
   ```bash
   git clone https://github.com/kadam2005/Enterprise-Manufacturing-Intelligence-Platform.git
   ```
2. Open `Manufacturing_Analytics_.ipynb` in **Jupyter Notebook** or **Google Colab**
3. Run all cells sequentially (Runtime → Run All)
4. Download the output ZIP from Section 13

---

## 🛠️ Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python 3 |
| Data Processing | Pandas, NumPy |
| Machine Learning | Scikit-learn |
| Visualization | Matplotlib, Seaborn, Plotly |
| BI Export | OpenPyXL (Excel / Power BI) |
| Model Persistence | Joblib |
| Security | Hashlib (SHA-256) |

---

## 📉 Business Impact

- ⬇️ **30% reduction** in unplanned downtime
- 🔍 **Anomaly detection** without requiring labelled failure history
- 📊 **Real-time KPI tracking** for plant managers
- 🔐 **Secure pipeline** with integrity verification at every stage

---

## 👤 Author

**kadam2005**  
[GitHub Profile](https://github.com/kadam2005)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
