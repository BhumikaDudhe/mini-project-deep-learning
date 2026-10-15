# Smart Energy Microgrid Forecaster (LSTM)

An end-to-end deep learning pipeline to forecast microgrid electricity load and optimize energy dispatch across Solar PV, Battery Storage (BESS), and the Main Grid.

---

## Overview

- **Dataset**: UCI Household Electric Power Consumption (2,075,259 raw minute records resampled to 34,589 hourly readings)[cite: 5].
- **Task**: Multi-step time-series forecasting (24-hour historical window $\rightarrow$ 4-hour forward load prediction)[cite: 5].
- **Architecture**: Stacked LSTM (64 and 32 units) with Dropout (0.2) and Dense output[cite: 5].
- **Optimizer & Loss**: Adam optimizer with MSE loss and Early Stopping[cite: 5].

---

## Results

| Metric | Test Value |
|---|---|
| **RMSE** | **0.5828 kW**[cite: 5] |
| **MAE** | **0.4228 kW**[cite: 5] |
| **SMAPE** | **43.80%**[cite: 5] |

---

## Smart Dispatch Logic

1. **Solar + Battery ⚡**: Selected when forecasted demand is balanced by simulated solar generation and battery reserves[cite: 5].
2. **Main Grid 🔌**: Selected for baseline loads during zero/low solar production without battery discharge incentives[cite: 5].
3. **Grid + Battery ⚡🔌**: Selected during peak load spikes to offset demand from the main grid via battery storage[cite: 5].

---

## Quick Start

```bash
# 1. Clone repository
git clone [https://github.com/BhumikaDudhe/Smart-Energy-Load-Forecasting-and-Management-in-Microgrid-Using-LSTM-Neural-Networks.git](https://github.com/BhumikaDudhe/Smart-Energy-Load-Forecasting-and-Management-in-Microgrid-Using-LSTM-Neural-Networks.git)
cd Smart-Energy-Load-Forecasting-and-Management-in-Microgrid-Using-LSTM-Neural-Networks

# 2. Install dependencies
pip install numpy pandas matplotlib scikit-learn tensorflow

# 3. Run Notebook
jupyter notebook DL_project.ipynb
