 Project Overview

This project implements an end-to-end Big Data Analytics pipeline using Apache Spark to process large-scale mobility data and develop scalable machine learning models for trip prediction.

The system covers:

Distributed Data Ingestion

Data Cleaning & Validation

Feature Engineering

Multiple Machine Learning Models

Cross-Validation & Statistical Testing

Scalability Analysis

Business Metric Alignment

Tableau Dashboard Visualization

The solution demonstrates both technical scalability and business impact alignment.

 Dataset

Source: U.S. Bureau of Transportation Statistics (BTS)
Dataset: Daily Mobility Statistics

Total processed records: 4,280,945 rows
Columns: 23
Storage format: Parquet (optimized for distributed processing)

 Architecture
🔹 Technology Stack

Apache Spark (Distributed Processing)

PySpark MLlib (Machine Learning)

Pandas (Statistical Evaluation)

Tableau Public (Visualization)

Jupyter Notebook (Development)

Parquet Storage Format

Spark UI (Execution Monitoring)

 Data Pipeline
 Data Ingestion

Data downloaded via API

2M+ rows retrieved in parallel batches

Stored as CSV (~416MB)

Converted to Parquet (~390MB compressed)

Data Cleaning & Validation

Performed:

Null value detection

Duplicate removal

Negative value validation

Outlier removal using IQR method

Division-by-zero safe handling

Schema validation

Validation Results:

Negative trips: 0

Duplicate rows: 0

Outliers removed: 677,760

Clean dataset: 4,280,945 rows

 Feature Engineering

Engineered Features:

Mobility ratio

Trip distribution bands

Monthly aggregation

One-hot encoding (if applicable)

VectorAssembler → Feature Vector creation

Final ML-ready dataset saved as:

data/final/mobility_ml_ready_v1 Machine Learning Models
Models Implemented





 Cross-Validation

3-Fold Cross Validation

Hyperparameter tuning:

numTrees: [30, 50]

maxDepth: [5, 10]

Best model selected based on RMSE.

 Statistical Significance

Performed:

Bootstrap Confidence Intervals

Model Stability Testing

Perturbation-based evaluation

Result: Model performance stable across samples.

 Scalability Analysis
Strong Scaling

Measured:

Training Time vs Partitions

Findings:

Performance improved with increased partitions

Minor overhead at high partition count

Bottleneck Identification

Memory pressure during Parquet writes

Shuffle partition tuning required

 Cost-Performance Tradeoff

Analyzed:

Training time vs RMSE

Computational efficiency vs prediction accuracy

Conclusion:
Random Forest provides best tradeoff between accuracy and compute cost.

 Tableau Dashboards

Four dashboards developed:

Dashboard 1 – Data Quality & Pipeline Monitoring

Null count visualization

Validation metrics

Data health KPIs

Dashboard 2 – Model Performance & Feature Importance

RMSE, MAE, R² KPIs

Feature importance ranking

Actual vs Predicted comparison

Dashboard 3 – Business Insights

Mobility trends

Forecast comparison

Business error metrics (MAPE)

Dashboard 4 – Scalability & Efficiency

Strong scaling visualization

Training time analysis

Performance vs partitions

 Spark UI Evidence

Spark UI used to validate:

Distributed execution

Task parallelism

Executor utilization
