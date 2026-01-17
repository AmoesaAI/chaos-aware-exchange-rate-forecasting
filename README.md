# Chaos-Aware Exchange Rate Forecasting

This repository contains code for **chaos-aware exchange rate forecasting** in emerging economies using a **Lévy-driven neural SDE (LDE-Net)** and **Lyapunov-based safe-horizon analysis**.

---

## Files

### Forecasting notebooks (LDE-Net)
Run the notebook for the country you want:

- `LDE_Net_Ghana_Experiment_1.2.ipynb`
- `LDE_Net_Nigeria_Experiment_1.2.ipynb`
- `LDE_Net_Gambia_Experiment_1.2.ipynb`
- `LDE_Net_SierraLeone_Experiment_1.2.ipynb`

Each notebook trains/evaluates **one-step-ahead** forecasts using the **LDE-Net** under a fixed Lévy stability parameter (e.g., `α = 1.2`) and reports forecast errors.

### Chaotic diagnostics (embedding + Lyapunov)
- `Embedding_and_Lyapunov.ipynb`

This notebook performs:
- **Phase Space Reconstruction** (τ = 1, m via Cao’s method)
- **Max Lyapunov exponent** estimation
- **Lyapunov time** computation (safe prediction horizon)

### Data
- `Exchange rate data.xlsx`

Contains daily USD exchange-rate series used by the notebooks.

---

## Quick Start

### 1) Install dependencies
```bash
pip install numpy pandas matplotlib scikit-learn torch openpyxl

### 2) Run Lyapunov / embedding analysis

Open and run:

- `Embedding_and_Lyapunov.ipynb`

This notebook performs:
- Phase Space Reconstruction (τ = 1, embedding dimension via Cao’s method)
- Maximum Lyapunov exponent estimation
- Computation of the Lyapunov time, interpreted as the **safe prediction horizon**

The resulting embedding dimension and Lyapunov time are used in the forecasting experiments.

---

### 3) Run forecasting (per country)

Open **one** of the country-specific notebooks, for example:

- `LDE_Net_Ghana_Experiment_1.2.ipynb`  
  (or the corresponding notebook for Nigeria, Gambia, or Sierra Leone)

Run all cells to reproduce:
- One-step-ahead exchange-rate forecasts
- Forecasting metrics (MSE / RMSE / MAE)
- Sensitivity results (where applicable)

---

## Notes

- The **Lyapunov time** is interpreted as a system-specific **safe prediction horizon**.
- Forecast accuracy is evaluated **within vs beyond** this horizon to demonstrate the
  predictability transition induced by intrinsic chaotic dynamics.

---

## Citation


This repository accompanies an under-review manuscript on chaos-aware exchange rate forecasting.
A BibTeX entry will be added upon publication or preprint release.

