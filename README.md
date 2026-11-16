# Demand Planning & Replenishment Automation (Perishables)

Seminar paper project for my M.Sc. in Supply Chain Management at SRH University.

**Question:** If you automate demand planning and replenishment for perishable products, what do you actually gain?

**Short answer:** Forecast accuracy stayed about the same as manual planning. The big gain was time: manual planning effort dropped by 96%.

## What I did

1. **Mapped the process** in BPMN 2.0, manual (As-Is) and automated (To-Be).
2. **Built a 6-script Python pipeline:**
   - data loading and cleaning
   - forecasting with Prophet against a seasonal-naive baseline
   - safety stock, reorder point and EOQ calculation
   - an FX and weather risk layer
   - output for replenishment decisions
3. **Compared** the two processes on accuracy, effort and cost.

## Results

| Metric | Result |
|---|---|
| Forecast error (MAPE) | 12.87% automated vs ~12.2% baseline |
| Manual planning effort | down 96% |
| Projected saving at 2,000 SKUs | ~13.1 FTE, ~€38k per month (German labour cost assumptions) |

Accuracy was not the win, and I say that openly. The win was speed, consistency and labour.

## Data (all open)

- FreshRetailNet-50K (retail demand for perishables)
- ECB exchange rates
- Open-Meteo weather data

## Tools

Python (Pandas, Prophet) · BPMN 2.0 · Excel

## Repo structure

```
data/          raw and cleaned data (or download script)
scripts/       01_load.py ... 06_output.py
bpmn/          As-Is and To-Be process models
results/       charts and tables
paper.pdf      seminar paper (if allowed to share)
```

## Run it

```
pip install -r requirements.txt
python scripts/01_load.py
...
```
