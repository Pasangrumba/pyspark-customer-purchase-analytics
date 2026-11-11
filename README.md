# Customer Purchase Analytics with PySpark

End-to-end big data analysis of customer purchase records using **Apache Spark (PySpark)**, **Spark SQL** and **Spark MLlib**, built for the Big Data Analytics module of my MSc Software Engineering at the University of West London.

## What it does

| Step | Technique |
|------|-----------|
| Ingest | Load CSV into a Spark DataFrame with schema inference |
| Clean | Median imputation for missing `SpendingScore` / `TotalPurchases`; remove rows with invalid zero values |
| Explore | Descriptive statistics, histogram, IQR outlier analysis, Pearson correlation |
| Query | Spark SQL aggregation by purchase category |
| Model | Decision Tree and Logistic Regression classifiers (Spark ML Pipelines with `StringIndexer` + `VectorAssembler`) |
| Evaluate | AUC-ROC, AUC-PR, RMSE, R² |

## Key results

- Cleaned 1,000 records down to **903 valid rows** (97 invalid rows removed).
- **Decision Tree AUC-ROC: 0.98**; Logistic Regression AUC-ROC: 0.93, AUC-PR: 0.82.
- `SpendingScore` is the strongest predictor of purchase outcome; `PurchaseAmount` and `SpendingScore` are not correlated (r = -0.02).
- Sports and Home & Kitchen have the highest average purchase value among customers under 50.

## Tech stack

Python · PySpark · Spark SQL · Spark MLlib · pandas · NumPy · Matplotlib · Jupyter

## Run it

Requires Python 3.9+ and Java 17 (Spark does not support Java 23+).

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cd notebooks && jupyter notebook customer_purchase_analysis.ipynb
```

## Project structure

```
data/customer_purchases.csv              # 1,000 customer purchase records
notebooks/customer_purchase_analysis.ipynb
requirements.txt
```

## Author

**Pasang Rumba** — Software Engineer, London · [LinkedIn](https://www.linkedin.com/in/pasang-rumba-45a02194/)
