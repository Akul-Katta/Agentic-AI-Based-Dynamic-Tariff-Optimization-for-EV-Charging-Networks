# Agentic AI-Based Dynamic Tariff Optimization for EV Charging Networks

## Overview

This project develops an Agentic AI framework for EV charging networks that combines demand forecasting, dynamic tariff optimization, and continuous performance monitoring.

Using historical charging-session data from the ACN-Data (Caltech) dataset, the system predicts future charging demand, adjusts tariffs according to demand levels, and evaluates pricing effectiveness through a monitoring feedback loop.

The objective is to improve charger utilization, increase operator revenue, reduce congestion, and encourage off-peak charging behavior.

---

## Project Architecture

The solution consists of three autonomous agents:

### 1. Demand Prediction Agent
Forecasts future charging demand using machine learning models trained on historical charging-session data.

Outputs:
- Predicted charging demand
- Expected utilization levels
- Congestion indicators

### 2. Tariff Pricing Agent
Converts demand forecasts into dynamic pricing decisions.

Pricing Strategy:
- Low Demand → ₹13
- Normal Demand → ₹16
- High Demand → ₹19

Pricing thresholds are determined using demand percentiles.

### 3. Monitoring & Learning Agent
Evaluates pricing outcomes and operational performance.

Tracks:
- Revenue Gain
- Off-Peak Uplift
- Waiting Time Reduction
- Customer Response Rate
- Pricing Efficiency Score

---

## Dataset

Dataset Used:
- ACN-Data (Adaptive Charging Network Dataset)
- Caltech EV Charging Sessions

Source:
https://ev.caltech.edu/dataset.html

Key Attributes:
- Connection Time
- Disconnection Time
- Energy Delivered (kWh)
- Session Duration
- Station Information
- User Information

---

## Project Workflow

### Step 1: Data Preprocessing
- Data cleaning
- Missing value handling
- Datetime conversion
- Session duration calculation

### Step 2: Exploratory Data Analysis
- Hourly demand analysis
- Monthly demand trends
- Peak-hour identification
- Charging behavior analysis

### Step 3: Feature Engineering
Generated features:
- Hour of Day
- Day of Week
- Month
- Lag-1 Demand
- Lag-2 Demand
- Lag-24 Demand
- Rolling 3-Hour Average
- Rolling 24-Hour Average

### Step 4: Demand Prediction
Model Used:
- CatBoost Regressor

### Step 5: Dynamic Pricing
Demand forecasts are mapped to pricing tiers using percentile-based thresholds.

### Step 6: Monitoring & Evaluation
Performance is continuously evaluated using operational and business metrics.

---

## Model Performance

| Metric | Value |
|----------|----------|
| RMSE | 0.638 |
| MAE | 0.251 |
| R² Score | 0.968 |

---

## Dynamic Pricing Results

| Metric | Value |
|----------|----------|
| Revenue Gain | 16.84% |
| Off-Peak Uplift | 169.17% |
| Waiting Time Reduction | 69.07% |
| Customer Response Rate | 21.8% |
| Pricing Efficiency Score | 15.97 |

---

## Repository Structure

```text
.
├── 01_data_preprocessing.ipynb
├── 02_EDA.ipynb
├── 03_feature_engineering.ipynb
├── 04_demand_prediction.ipynb
├── 05_dynamic_pricing.ipynb
│
├── caltech.csv
├── processed_caltech.csv
├── evaluation_metrics.csv
├── requirements.txt
└── README.md
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/Agentic-AI-EV-Dynamic-Pricing.git
cd Agentic-AI-EV-Dynamic-Pricing
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Running the Project

Execute notebooks in the following order:

```text
1. 01_data_preprocessing.ipynb
2. 02_EDA.ipynb
3. 03_feature_engineering.ipynb
4. 04_demand_prediction.ipynb
5. 05_dynamic_pricing.ipynb
```

---

## Key Assumptions

- Demand forecasts are generated using historical charging-session patterns.
- Customer response is approximated through demand elasticity proxies.
- Waiting-time and congestion impacts are estimated through utilization-based simulations.
- Weather, holidays, electricity prices, and other external factors are excluded.
- Dynamic pricing outcomes are evaluated against a fixed-pricing baseline.

---

## Limitations

- Results are based on historical charging-session data.
- Customer behavior is approximated rather than directly observed.
- Revenue and congestion impacts are simulation-based.
- Real-world deployment and A/B testing were not conducted.
- External environmental variables were not incorporated.

---

## Future Work

- Reinforcement Learning-based pricing optimization
- Real-time demand forecasting
- Multi-station network optimization
- Integration with live charger occupancy data
- Electricity market and grid-aware pricing

---

## Author

Project Title:
**Agentic AI-Based Dynamic Tariff Optimization for EV Charging Networks**

Developed as part of the SOCBIZ Open Project.
