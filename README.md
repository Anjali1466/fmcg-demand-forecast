# FMCG Demand Forecasting — SKU-Level Stockout Risk Predictor

**Author:** Pamar | IIT Madras | Chemical Engineering  
**GitHub:** [pamarz](https://github.com/pamarz)

---

## Problem Statement

FMCG companies lose revenue due to stockouts and overstock situations. This project forecasts weekly SKU-level demand and flags products at high stockout risk — enabling smarter replenishment decisions.

---

## Dataset

- **3,660 rows** | Weekly sales data (2021–2024)
- **5 SKUs:** Detergent Powder, Shampoo, Soap Bar, Instant Coffee, Biscuits
- **4 Regions:** North, South, East, West
- **Features:** units_sold, price_inr, promo_flag

---

## Methodology

| Step | Method |
|---|---|
| Forecasting | Meta Prophet (multiplicative seasonality) |
| Holiday Effect | Indian festivals — Diwali, Holi, Navratri |
| Stockout Risk | Reorder Point = Avg Demand × Lead Time + Safety Stock |
| Risk Levels | HIGH / MEDIUM / LOW per SKU-Region pair |

---

## Outputs

| File | Description |
|---|---|
| `outputs/forecast_full.csv` | Full forecast with confidence intervals |
| `outputs/stockout_risk_next12weeks.csv` | 12-week stockout risk per week |
| `outputs/all_sku_risk_summary.csv` | Risk summary across all 20 SKU-Region combinations |
| `outputs/demand_forecast_chart.png` | Forecast + risk visualization |

---

## How to Run

```bash
pip install pandas numpy prophet matplotlib scikit-learn
python generate_dataset.py
python forecast.py
```

Change `TARGET_SKU` and `TARGET_REGION` in `forecast.py` to analyze any product-region combo.

---

## Key Results

- Demand for **Detergent Powder** peaks in summer (+25%) and during Diwali (+15%)
- Reorder point calculated dynamically using historical mean + safety stock buffer
- Stockout risk flagged 12 weeks in advance for proactive supply chain action

---

## Skills Demonstrated

`Python` `Prophet` `Time Series Forecasting` `Supply Chain Analytics` `FMCG Domain` `Pandas` `Matplotlib`

---

## Relevance

This project is directly applicable to supply chain and operations roles at **HUL, P&G, ITC, Nestle, Marico, Dabur** — companies that run SKU-level demand planning at scale.
