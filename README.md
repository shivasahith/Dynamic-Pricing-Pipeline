# Dynamic Product Pricing – Bronze/Silver/Gold Pipeline

## Summary
This project demonstrates a **dynamic pricing pipeline** on **Databricks** using an Amazon sales dataset.  
https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset

It follows the **Bronze–Silver–Gold architecture** with monitoring, feature engineering, and suggested pricing logic.

- **Bronze:** Raw ingestion of CSV (uncleaned).  
- **Silver:** Cleaned & standardized schema (numeric prices/ratings). Includes data quality checks.  
- **Gold:** Suggested pricing using **anchor products** (top 10% by popularity).  
- **Serving:** Comparison view of `actual_price vs anchor_median_price vs suggested_price`.  

##  Setup Instructions
1. Clone this repository:
   ```bash
   git clone https://github.com/shivasahith/Dynamic-Pricing-Pipeline.git

Open the notebook in Databricks.

Upload the dataset (amazon.csv from Kaggle) to your Databricks workspace.

Adjust the file path in the Bronze ingestion cell to match your environment.

## How to Run

Run cells in order:

Bronze ingestion

Silver cleaning (₹, %, commas → numeric types)

Monitoring checks

Feature engineering (popularity score)

Gold pricing (anchors + suggested prices)

Comparison view

The final Gold table is saved as amazon_gold_pricing.

Use display(comparison) to view actual vs suggested prices.

## Key Features

Data Quality Checks (nulls, invalid prices)

Feature Engineering: popularity score = rating × rating_count

Anchor Pricing Strategy (top 10% anchors)

Suggested Price Formula: 0.9 * anchor_median_price + 0.1 * actual_price

Serving Layer: final Gold table and comparison view

## Tools & Tech

Databricks (Serverless cluster)

PySpark + Delta Lake

Kaggle Dataset
 

## Future Improvements

Add streaming ingestion (Kafka → Spark Structured Streaming)

Train an ML model for optimized pricing weights

Integrate alerts/dashboards in Databricks Jobs

Deploy pricing API for real-time serving
