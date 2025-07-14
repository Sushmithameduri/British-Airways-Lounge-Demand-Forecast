# British Airways Lounge Demand Forecast

## Overview

This repository contains data science solutions for analyzing and forecasting British Airways lounge demand, structured into two main tasks:

- **Task 1: Lounge Prediction**  
  Forecasts future lounge demand using historical passenger and booking data.

- **Task 2: Customer Holiday Buying Behaviour Model Forecast**  
  Models and predicts customer booking completion behaviour to understand and anticipate holiday travel demand.

---

## Objectives

- **Task 1:**  
  Predict lounge occupancy to optimize staffing, provisioning, and customer experience.

- **Task 2:**  
  Identify key drivers of booking completion and forecast customer holiday buying patterns.

---

## Methodologies

- **Data Exploration & Cleaning:**  
  Inspected, cleaned, and preprocessed raw datasets for analysis.

- **Feature Engineering:**  
  Created new variables (e.g., time-of-day, trip type, extra services) to enhance model performance.

- **Time Series Forecasting (Task 1):**  
  Applied statistical and machine learning models (e.g., ARIMA, Random Forest) to predict lounge demand.

- **Classification Modeling (Task 2):**  
  Used Random Forest classifiers and hyperparameter tuning to predict booking completion.

- **Evaluation & Visualization:**  
  Assessed models using accuracy, ROC AUC, and visualized key trends and feature importances.

---

## Key Findings

### Task 1: Lounge Prediction
- **Lookup Table Structure:**
  - Segmented by haul type (LONG/SHORT) and time periods (Morning/Afternoon/Evening/Lunchtime)
  - Tier-wise passenger eligibility percentages:
    * LONG haul:
      - Tier 1: 0.19-0.23%
      - Tier 2: 2.87-2.95%
      - Tier 3: 10.98-11.26%
    * SHORT haul:
      - Tier 1: 0.33-0.39%
      - Tier 2: 4.31-4.55%
      - Tier 3: 16.59-17.28%
  
- **Demand Patterns:**
  - Short-haul flights show significantly higher tier eligibility:
    * ~1.5x higher Tier 1 percentage
    * ~1.5x higher Tier 2 percentage
    * ~1.5x higher Tier 3 percentage
  - Time of day variations:
    * Lunchtime peaks for short-haul (17.28% Tier 3)
    * Morning peaks for long-haul (11.26% Tier 3)
  - Total lounge demand highest for:
    * SHORT - Lunchtime: 22.22% of passengers
    * SHORT - Morning: 21.44% of passengers
    * LONG - Morning: 14.43% of passengers

- **Business Impact:**
  - Clear distinction between long and short-haul demands
  - Time-of-day patterns enable precise resource allocation
  - Higher tier eligibility in short-haul requires focused capacity

### Task 2: Booking Behavior Model
- **Optimized Model Parameters:**
  - n_estimators: 300
  - max_depth: 20
  - min_samples_split: 15
  - min_samples_leaf: 1

- **Model Performance Metrics:**
  | Metric    | Baseline | Tuned  | Improvement |
  |-----------|----------|--------|-------------|
  | Accuracy  | 84.37%   | 84.42% | +0.05%     |
  | Precision | 45.12%   | 45.28% | +0.16%     |
  | Recall    | 25.95%   | 26.12% | +0.17%     |
  | F1-Score  | 32.95%   | 33.15% | +0.20%     |
  | ROC AUC   | 0.7722   | 0.7742 | +0.0020    |

- **Top Feature Importance:**
  1. Booking origin (0.208)
  2. Route (0.147)
  3. Purchase lead time (0.121)
  4. Length of stay (0.096)
  5. Flight hour (0.081)
  6. Flight duration (0.070)
  7. Flight day (0.051)
  8. Number of passengers (0.029)
  9. Flight time category (0.028)
  10. Total extras (0.027)

- **Key Business Insights:**
  - Booking origin and route are strongest predictors
  - Purchase lead time remains significant predictor
  - Time-based features show moderate importance
  - Model demonstrates stable cross-validation performance (ROC AUC: 0.7684 ±0.0215)
---

## Technologies Used

- Python (pandas, numpy, matplotlib, seaborn, scikit-learn, statsmodels)
- Jupyter Notebook / VS Code
- Git for version control

---

## Repository Structure

- `data/` — Raw datasets
- `task 1/` — Lounge demand prediction notebooks and scripts
- `task 2/` — Customer booking behaviour modeling notebooks and scripts
- `requirements.txt` — Python dependencies

---

## Getting Started

1. Clone the repository.

   ```bash
   git clone https://github.com/yourusername/British-Airways-Lounge-Demand-Forecast.git
   cd British-Airways-Lounge-Demand-Forecast
   ```

2. Set up Python environment and install dependencies:
   ```bash
   conda create -n ba-lounge python=3.10
   conda activate ba-lounge
   pip install -r requirements.txt
   ```

3. Open the notebooks:
   - For lounge demand prediction:
     ```bash
     code "task 1/lookup table.ipynb"
     ```
   - For booking behavior analysis:
     ```bash
     code "task 2/code.ipynb"
     ```

4. Run the notebooks:
   - Select the `ba-lounge` kernel in VS Code
   - Run all cells sequentially (Shift + Enter)
   - View results in the integrated outputs

---
